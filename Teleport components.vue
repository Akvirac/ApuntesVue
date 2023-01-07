<!-- Usamos el teleport tag, para que en caso de tener que utilizar algun popup o algo que necesite configuraciones de css totalmente libres a la hora de mostrarse en la pagina, de esta forma, hacemos que se monte una mini app dentro de nuestra misma app. Lo primero que hay que hacer es agregar esto en nuestro index en public <div id="portal-root"></div> debajo de el div similar a este pero con el id app. -->
<template>
	<!-- Llamamos al portal y colocamos el componente que queremos hacer que funcione aparte dentro. -->
	<teleport to="#portal-root">
		<Portal />
	</teleport>
</template>

<script>
//importamos nuestros componentes.
import Portal from './components/Portal.vue'

export default {
	name: 'App',
	components: {
		//Agregamos el componente a la lista.
		Portal,
	},
	data() {
		return {
			activeTab: 'TabA',
		}
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
