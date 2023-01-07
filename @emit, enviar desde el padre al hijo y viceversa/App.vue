<!-- Lo que queremos hacer en esta clase, es poder enviar informacion al hijo desde nuestro padre app y tambien poder enviar informacion o pedidos desde el hijo para que se realicen procesos en el padre. esto lo realizamos de la siguiente manera. -->
<template>
	<button @click="showPopUp = true">Show PopUp</button>
	<!-- Aca creamos un boton con la funcion para que setee la caracteristica showpopup a verdad, lo cual seteamos primero como falsa. al tocar el boton, se ejecuta. -->
	<PopupButton v-show="showPopUp" @close="closePopUp" />
	<!-- Creamos la conexion v-show, para hacer la funcion de aparecerlo. -->
	<!-- luego creamos el listner con la orden close, que recibimos desde nuestro hijo el cual setea de nuevo la funcion a falsa, para que cuando el boton del hijo de la orden, el popup desaparezca. -->
</template>

<script>
import PopupButton from './components/PopupButton.vue'

export default {
	name: 'App',
	components: {
		PopupButton,
	},
	data() {
		return {
			showPopUp: false,
		}
		// Creamos en data el show que seria falso para que no este visible.
	},
	methods: {
		closePopUp(name) {
			this.showPopUp = false
			console.log('name', name)
			//aca recibimos el nombre ingresado en nuestro hijo, para mostrarlo en la consola.
		},
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
