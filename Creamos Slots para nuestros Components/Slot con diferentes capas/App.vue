<!-- Lo que vamos a hacer a continuacion es utilizar la caracteristica <slot></slot> la cual nos permite controlar el contenido de nuestros componentes desde la app.vue-->
<template>
	<!-- como vemos cremos un componente CardComponent, el cual repetimos 3 veces, dandole diferentes contenidos. En el componente vamos a ver como se hace. Pero un dato principal es que hacemos open y close tags de nuestro componente y el contenido va dentro de ellos. -->
	<CardComponent></CardComponent>
	<CardComponent>Card Content</CardComponent>
	<CardComponent><h2>Card Content</h2></CardComponent>
	<CardComponent>
		<img src="./assets/logo.png" />
	</CardComponent>
	<!-- En este ultimo CardComponent, lo que hacemos es al mismo componente, darle diferentes partes, en este caso 3, un header, content y footer. para ir agregandole informacion. -->
	<!-- Podemos ver que se dividen en templates con el nombre que nosotros le asignemos a nuestros div en el componente. Tener en cuenta que siempre puede haber un default solo, al resto hay que nombrarlos. -->
	<CardComponent>
		<template v-slot:header>
			<h3>header</h3>
		</template>
		<template v-slot:default>
			<img src="./assets/logo.png" />
		</template>
		<template v-slot:footer>
			<button>View Details</button>
		</template>
	</CardComponent>
	<NameList></NameList>
</template>

<script>
//importamos nuestros componentes.
import CardComponent from './components/CardComponent.vue'
import NameList from './components/NameList.vue'
export default {
	name: 'App',
	components: {
		//Lo añadimos a components.
		CardComponent,
		NameList,
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
