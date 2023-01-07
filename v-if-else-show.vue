<template>
	<h2 v-if="num === 0">The number is zero</h2>
	<!-- aca lo que hacemos, es crear un numero en nuestra data, para luego, si ese numero es 0, mostrar el mensaje de que es cero, en caso contrario el h2, no se mostraria nunca. -->
	<h2 v-else-if="num < 0">the number is negative</h2>
	<h2 v-else-if="num > 0">the number is positive</h2>
	<h2 v-else>Not a number</h2>
	<!-- aca vemos que si utilizamos un else, que seria en caso de que no entre el if, salte este h2, el cual se encarga de decir que no es 0, siempre tiene que ser consecutivo al if, si no no funciona. -->
	<!-- de esta forma, lo que hacemos, es empezar de a poquito, a hacer contenidos de nuestro html, visible o no, ya que si el numero es 0, mostraremos un h2, en caso contrario, mostramos el otro. -->
	<template v-if="display === true">
		<h2>Vishwas</h2>
		<h2>Codevolution</h2>
		<h2>Vue</h2>
	</template>
	<!-- aca podemos ver que, en caso de querer utilizar varios tags de html juntos en un solo if, podemos unirlos con un template, es una forma de hacerlo en vue. ya que utilzar un div, nos podria hacer complicar un poco las cosas o provocar futuros errores. -->
	<h2 v-show="showElement">Using v-show</h2>
	<!-- de esta forma lo que hacemos, es similar al if, en todo sentido, menos 1, que cuando usamos el v-show, el tag al que nosotros le asignamos el v-show, se carga en el dominio, pero no se muestra, por caso contrario, el if, lo que hace, en caso de no entrar al mismo, directamente no ejecuta nada en el dominio, no lo oculta, si no que directamente no lo randeriza. -->
	<!-- por eso mismo, si hay cosas que van a aparecer y desaparecer todo el tiempo, lo mejor es utilizar el v-show, para que la pagina sea mas optima. -->
</template>

<script>
export default {
	name: 'App',
	data() {
		return {
			num: 0,
			display: true,
			showElement: true,
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
