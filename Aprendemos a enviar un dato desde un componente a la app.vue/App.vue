<!-- En estos archivos lo que hacemos en crear un input como componente y utilizarlo para recibir informacion desde el mismo a nuestra app.vue. -->
<template>
	<!-- Llamamos la componente y le agregamos el v-model y a que variable le vamos a asignar el valor que tenga name. -->
	<InputComponent v-model="name" />
</template>

<script>
//importamos el componente
import InputComponent from './components/InputComponent.vue'
export default {
	name: 'App',
	components: {
		//Agregamos el componente a components.
		InputComponent,
	},
	data() {
		return {
			//Creamos la variable que vamos a utilizar.
			name: '',
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
