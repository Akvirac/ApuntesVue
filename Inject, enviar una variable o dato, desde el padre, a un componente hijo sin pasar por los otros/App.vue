<template>
	<h3>AppComponent username {{ name }}</h3>
	<ComponentC />
</template>
<!-- Basicamente lo que hacemos en esta etapa de el curso, es conectar un dato anidado, dentro el nuestra app principal y con el comando inject enviarlo directamente a el ComponentF, lo cual en otros casos sin el comando tendriamos que anviarlo primero por el C, luego el E y finalmente al F. -->

<script>
import ComponentC from './components/ComponentC.vue'

export default {
	name: 'App',
	components: {
		ComponentC,
	},
	data() {
		return {
			name: 'Vishwas',
			//Nombre creado para almacenarlo y luego transformalo a nombre de usuario mas abajo.
			// Nos preguntamos porque no podemos llamar directamente a username en nuestro template principal y es porque el inject no deja utilizarlo en el principal, solo en el hijo al cual se envia.
		}
	},
	provide() {
		return {
			username: this.name,
			//Aca pedimos el dato name a data, para hacerlo el username, de esta forma obtenerlo y enviarlo.
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
