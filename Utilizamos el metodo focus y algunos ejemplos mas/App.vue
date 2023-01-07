<template>
	<TemplateRef />
</template>

<script>
//importamos nuestros componentes.
// import PostList from './components/PostList.vue'
// import CreatePost from './components/CreatePost.vue'
import TemplateRef from './components/TemplateRef'

export default {
	name: 'App',
	components: {
		//Agregamos el componente a la lista.
		// PostList,
		// CreatePost,
		TemplateRef,
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
