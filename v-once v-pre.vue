<template>
	<h2 v-once>{{ name }}</h2>
	<button @click="name = 'Batman'">Change name</button>
	<!-- Con la directiva v-once lo que hacemos, es que donde nosotros la utilicemos, ese pedacito de codigo, se actualice solo una vez, por eso, hacemos lo de cambiar a batman, para demostrar, que al cargar la pagina, sin el v-once, podemos modificar el nombre por su constante actualizacion, pero si ponemos el modifier, no funciona, ya que solo se randeriza una sola vez. -->
	<h2 v-pre>{{ name }}</h2>
	<!-- Con v-pre lo que hacemos, es evitar que el html compile nuestro elemento, por ende queda solamente puro html. Mas que nada, esto sirve para en casos que tengamos en nuestra pagina, mucho html sin nada de vue por detras, lo que hace es evitar que se recorra toda esa porcion de codigo, optimizando su funcionamiento. -->
</template>

<script>
export default {
	name: 'App',
	data() {
		return {
			name: 'Ariel',
		}
	},
	methods: {},
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
