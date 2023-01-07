<!-- En este caso vamos a utilizar los slots, para darle un poco mas de control a la app.vue sobre un componente con nombres. -->
<template>
	<!-- Creamos el componente NameList el cual vamos a llamar 3 veces y la particularidad es que le vamos a pasar datos desde el componente a su padre, en este caso app.vue, voy explicar como funciona 1. -->
	<NameList>
		<template v-slot:default="slotProps">
			{{ slotProps.firstName }} {{ slotProps.lastName }}
		</template>
		<!-- como podemos ver, utilizamos el v-slot para recibir la informacion que hay que nuestro componente, de esta forma, la recibimos y la ordenamos con las llaves segun su nombre y orden que querramos. Explicamos un poquito mas en el componente.-->
	</NameList>
	<NameList>
		<template v-slot:default="slotProps">
			{{ slotProps.lastName }}
			{{ slotProps.firstName }}
		</template>
	</NameList>
	<NameList>
		<template v-slot:default="slotProps"> {{ slotProps.firstName }} </template>
	</NameList>
</template>

<script>
//importamos nuestros componentes.
import NameList from './components/NameList.vue'
export default {
	name: 'App',
	components: {
		//Lo añadimos a components.
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
