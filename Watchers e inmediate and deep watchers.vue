<template>
	<h2>Volume Tracker (0-20)</h2>
	<h3>Current Volume - {{ volume }}</h3>
	<div>
		<button @click="volume += 2">Increase</button>
		<button @click="volume -= 2">Decrease</button>
		<!-- en este template, simplemente creamos una variable llamada volume, a la cual le subimos 2 o le bajamos 2, la cual seria una simulacion de un volumen de algo. -->
	</div>
	<input type="text" v-model="movie" />
	<!-- Creamos un input donde cargaremos el nombre de una pelicula cualquiera, para hacer una prueba con el watcher. -->
	<input type="text" v-model="movieInfo.title" />
	<input type="text" v-model="movieInfo.actor" />
	<button @click="movieList.push('Wonder Woman')">Add Movie</button>
	<!-- aca lo que hacemos es agregar un boton que sume la pelicula wonder woman a el array movieList, esto lo hacemos con el listner @click, para que luego nuestro watcher desencadene el evento de mostrarlo en consola. -->
	<button @click="movieList = movieList.concat(['Wonder Woman'])">
		Add Movie
	</button>
	<!-- A diferencia del boton anterior, este directamente agrega wonder woman a el array, por ende, no es necesario utilizar el deep:true, pero como se puede ver, no es un push si no un concat. -->
</template>

<script>
export default {
	name: 'App',
	data() {
		return {
			volume: 0,
			// variable creada nombrada arriba.
			movie: '',
			movieInfo: {
				title: '',
				actor: '',
			},
			movieList: ['Batman', 'Superman'],
		}
	},
	methods: {},
	computed: {},
	watch: {
		// Los watchers se crean en un objeto aparte a los metodos y computeds, tiene su espacio determinado. Los mismos son similares a las computed propertys, pero son mas especificas de reaccionar a cambios en datos.
		volume(newValue, oldValue) {
			if (newValue > oldValue && newValue === 8) {
				//En esta logica, lo que hacemos, en la primera parte es comprobar que el usuario este subiendo el volumen, para que en caso de que lo este bajando, no salte la alerta y si se cumplen las 2 condiciones, la de que el usuario esta subiendo el volumen y el valor es 8, salta la alerta correspondiente.
				alert(
					'Listening to a high volume for a long time, maybe cause damage to your hearing.'
				)
				// Aca lo que estamos haciendo es que a determinado valor de nuestra variable la pagina nos muestre una alerta, supongo que esta alerta podria ser cambiada por cualquier otro evento que quisieramos desencadenar.
			}
		},
		//Siempre a la hora de utiliazar los watcher, hay que observar que esten a la misma altura, ya que si lo usamos dentro de otro, no va a funcionar.
		movie: {
			handler(newValue) {
				console.log(`Calling API with movie name = ${newValue}`)
			},
			inmediate: true,
		},
		//Aca aplicamos un watcher para poder ir llamando a una variable o desencadenando eventos, que en este caso, solamente hacemos que salte un mensaje en la consola cada vez que se modifica la variable, en resumen, desencadena el evento que nosotros querramos.
		movieInfo: {
			handler(newValue) {
				console.log(
					`Calling API with movie title = ${newValue.title} and actor = ${newValue.actor}`
				)
				//En este caso lo que vamos a hacer es, observar las 2 variables que contiene el objeto movieInfo, como el watcher no ingresa automaticamente cuando es un objeto, debemos usar la caracteristica de abajo.
			},
			deep: true,
			//Si nosotros seteamos esta caracteristica a nuestro watcher, va a observar los cambios dentro de un objeto, de lo contrario no sucedera nada.
		},
		movieList: {
			handler(newValue) {
				console.log(`Updated list ${newValue}`)
			},
			deep: true,
			//En este caso lo que hacemos, es crear un array de peliculas, llamado movieList, que contiene 2 peliculas, a las cuales le sumamos otra, con nuestro watcher lo que hacemos, es que al agregarse un dato nuevo a ese array, nos muestre en consola la lista completa y actualizada.
			//hay que usar nuevamente el deep:true para poder acceder al array.
		},
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
