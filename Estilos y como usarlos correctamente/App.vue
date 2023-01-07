<!-- En este archivo vamos a trabajar sobre los estilos en los componentes, los cuales, vemos que se aplican globales, sin importar si estan aplicados desde un componente o desde app.vue -->
<!-- Por este motivo vamos a aprender a hacerlos por separado tanto global como local. -->
<!-- Si desde los 2 archivos, tanto padre como hijo se aplican diferentes estilos, lo que va a pasar es que queda el estilo del padre, por orden de lectura, siempre se lee primero el hijo luego el padre. -->
<template>
	<h4>add component text</h4>
	<!-- Hay que tener en cuenta tambien, que si utilizamos un slot, el estilo que va a dominar es el asignado en el padre, a pesar de tener scope y los divs aplicados en el componente. -->
	<ChildStyles><h4>Childstyle component text</h4> </ChildStyles>
</template>

<script>
//importamos nuestros componentes.
import ChildStyles from './components/ChildStyles.vue'
export default {
	name: 'App',
	components: {
		//Lo añadimos a components.
		ChildStyles,
	},
	data() {
		return {}
	},
	methods: {},
}
</script>

<!-- con el tag scoped, lo que hacemos es aplicar solamente a este archivo las modificaciones visuales de css, hay que tener en cuenta para no tener conflictos en agregarlo a todos los componentes. -->
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
h4 {
	color: orange;
}
</style>
