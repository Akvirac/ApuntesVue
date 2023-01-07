<template>
	<div>{{ greet }} {{ name }}</div>
	<!-- hacemos un texto a traves de datos en data, usando las llaves -->
	<div v-html="channel"></div>
	<!-- aca lo que hacemo es llamar a un texto a traves de el nombre en data -->
	<h2 :id="headingId">Heading</h2>
	<!-- /* aca agregamos un id a un h2, para poder llamarlo de alguna forma. */ -->
	<button :disabled="isDisable">Bind</button>
	<!-- habilitamos o viseversa un boton segun su valor boleano -->
	<h2 class="underline">Underline text</h2>
	<!-- aplicamos una clase a traves de class -->
	<h2 class="underline" :class="status">Status</h2>
	<!-- le aplicamos una clase a un texto y agregamos un dato para utilizar -->
	<h2 :class="isPromoted && 'promoted'">Promoted Movie</h2>
	<!-- utilizamos un valor boleano para aplicar o no un estilo a el texto -->
	<h2 :class="isSoldout ? 'sold-out' : 'new'">Soldout movie</h2>
	<!-- si una caracteristica en particular de el dato, hace que cambie de color, si esta soldout o no. -->
	<h2 :class="['new', 'promoted']">Newly promoted movie</h2>
	<!-- aplicamos 2 estilos diferentes a un mismo texto a traves de v-bind:class -->
	<h2 :class="[isPromoted && 'promoted', isSoldout ? 'sold-out' : 'new']">
		Conditional Movie
	</h2>
	<!-- aca lo que hacemos, es aplicar estilos segun el estado de las respuestas boleanas -->
	<h2
		:class="{
			promoted: isPromoted,
			new: !isSoldout,
			'sold-out': isSoldout,
		}"
	>
		Objet conditional movie
	</h2>
	<!-- aca lo que hacemos, es aplicar las mismas caracteristicas que en la conditional movie, pero creando un objeto dentro de class, donde pregunta directamente si se cumplen ciertas condiciones para darle determinados estilos a object conditional movie. -->
	<h2
		:style="{
			color: highlightColor,
			'font-size': headerSize + 'px',
			padding: '20px',
		}"
	>
		Inline Style
	</h2>
	<!-- aca lo que vemos es como podemos aplicar diferentes estilos, aparte de poder agregar estilos como padding directamente sin estar en data, estos estilos en lugar de llamarlos desde el css, lo llamamos desde data. -->
	<h2 :style="headerStyleObject">Style objetc</h2>
	<!-- aca lo que hacemos es aplicar exactamente los mismos estilos, pero creando un objeto en nuestra data, donde contiene las 3 caracteristicas, quedando mucho mas limpio nuestro HTML. -->
	<div :style="[baseStyleObject, successStyleObject]">Success Style</div>
	<!-- agregamos diferentes objetos de estilos a un div, podemos ver que usamos un array que contiene los estilos, tener en cuenta que si hay estilos que sean iguales, siempre usara el ultimo, seria en modo cascada -->
	<div :style="[baseStyleObject, dangerStyleObject]">Success Style</div>
	<!-- hacemos lo mismo que arriba, pero manteniendo el orden semantico de las cosas, podemos ver que sigue aplicando los estilos que se adquieren ultimos. -->
	<!-- podemos no utilizar el v-bind, solo con utilizar :class por ejemplo, ya estariamos llamando al v-bind, es para optimizar codificacion. -->
</template>

<script>
export default {
	name: 'App',
	data() {
		return {
			greet: 'hello',
			name: 'Batman',
			channel: '<b>Codevolution</b>',
			headingId: 'heading',
			isDisable: false,
			status: 'danger',
			isPromoted: false,
			isSoldout: true,
			highlightColor: 'orange',
			headerSize: 50,
			headerStyleObject: {
				color: 'orange',
				fontSize: '50px',
				padding: '20px',
			},
			baseStyleObject: {
				fontSize: '50px',
				padding: '10px',
			},
			successStyleObject: {
				color: 'green',
				backgroundColor: 'lightgreen',
				border: '1px solid green',
				padding: '20px',
			},
			dangerStyleObject: {
				color: 'darkred',
				backgroundColor: 'red',
				border: '1px solid darkred',
			},
		}
	},
}
</script>

<style>
#app {
	font-family: Avenir, Helvetica, Arial, sans-serif;
	-webkit-font-smoothing: antialiased;
	-moz-osx-font-smoothing: grayscale;
	text-align: center;
	color: #2c3e50;
	margin-top: 60px;
}
.underline {
	text-decoration: underline;
}
.promoted {
	font-style: italic;
}
.new {
	color: green;
}
.sold-out {
	color: red;
}
</style>
