<!-- Ahora lo que vamos a hacer es hacer una HTTP get request, lo que seria pedir informacion a una pagina o un servidor, para nosotros utilizarla en nuestra app. -->
<!-- Donde montamos todos nuestros componentes. -->
<template>
	<PostList />
	<CreatePost />
</template>

<script>
//importamos nuestros componentes.
import PostList from './components/PostList.vue'
import CreatePost from './components/CreatePost.vue'

export default {
	name: 'App',
	components: {
		//Agregamos el componente a la lista.
		PostList,
		CreatePost,
	},
	data() {
		return {}
	},
	methods: {},
}
</script>

<style scoped>
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
