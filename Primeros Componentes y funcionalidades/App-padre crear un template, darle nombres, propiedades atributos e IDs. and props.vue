<template>
	<GreetPage name="Bruce" heroName="Batman" />
	<!-- Para darle un nombre diferente a cada hello que tenemos en nuestro GreetPage, lo que hacemos le damos una variable que contiene el nombre correspondiente. Luego procedemos al componente en cuestion. De esta forma estamos pasando datos estaticos a nuestro componente.-->
	<GreetPage name="Clark" heroName="Superman" />
	<GreetPage name="Diana" heroName="Wonder Woman" />
	<!-- Llamamos a el componente dentro de nuestro template principal en App.vue -->
	<!-- Nosotros podemos llamar este componente las veces que sean necesarias, solo con escribirlo ya lo estamos sumando a nuestro template. -->
	<GreetPage :name="name" :heroName="channel" />
	<!-- En este ultimo GreetPage, lo que hacemos es hacer dinamico a nuestro componente, ya que esta llamando a las variables que tenemos en data. Recordar que tenemos que usar el v-bind, el cual se hace con : antes de el nombre la propiedad. -->
	<ArticlePage
		id="my-article"
		title="Article Title"
		:likes="50"
		:isPublished="true"
	/>
	<!-- Cuando nosotros le damos un id a un componente, lo que hace el mismo, es asignarselo a el div que contenga dentro el componente, por ende si no tenemos un div, dentro, no va a funcionar. -->
	<!-- Lo que hacemos en este componente es mostrar que podemos utilizar de otra forma el props, para facilitar la lectura del codigo. Mas detalles en el componente.-->
	<!-- En el caso de los likes, tenemos que hacer un v-bind, por el hecho de que estamos pasando un numero, si no lo hacemos la pagina va a funcionar, pero en consola nos va a saltar que espera un numero no un string, es mas, vamos a ver que si hacemos el v-bind, el numero pasa a verse de el color caracteristico del mismo. -->
	<!-- Por ultimo pasamos un valor booleano a nuestro componente hijo, el cual recibimos alla y aplicamos a nuestro HTML. -->
</template>

<script>
import GreetPage from './components/GreetPage.vue'
import ArticlePage from './components/ArticlePage.vue'
// Lo importamos dentro de nuestro script

export default {
	name: 'App',
	components: {
		GreetPage,
		ArticlePage,
	},
	data() {
		return {
			name: 'Vishwas',
			channel: 'Codevolution',
			//Creamos las 2 variables que vamos a llamar desde nuestro componente.
		}
	},
	// Llamamos a nuestro component dentro de el export default, siempre recordando mantener el mismo nombre respetando las mayus si no no va a funcionar.
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
