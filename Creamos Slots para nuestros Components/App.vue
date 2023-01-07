<!-- Lo que vamos a hacer a continuacion es utilizar la caracteristica <slot></slot> la cual nos permite controlar el contenido de nuestros componentes desde la app.vue-->
<template>
	<!-- como vemos cremos un componente CardComponent, el cual repetimos 3 veces, dandole diferentes contenidos. En el componente vamos a ver como se hace. Pero un dato principal es que hacemos open y close tags de nuestro componente y el contenido va dentro de ellos. -->
	<CardComponent></CardComponent>
	<CardComponent>Card Content</CardComponent>
	<CardComponent><h2>Card Content</h2></CardComponent>
	<CardComponent>
		<img src="./assets/logo.png" />
	</CardComponent>
</template>

<script>
//importamos nuestro componente.
import CardComponent from './components/CardComponent.vue'
export default {
	name: 'App',
	components: {
		//Lo añadimos a components.
		CardComponent,
	},
	data() {
		return {}
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
