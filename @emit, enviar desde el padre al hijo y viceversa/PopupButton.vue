<template>
	<div>
		<h2>This is a popup</h2>
		<input type="text" v-model="name" />
		<!-- ahora procedemos en nuestro component, eliminar el cargado automatico del nombre a hacer un input, donde cargamos un nombre, para almacenarlo en la data name, para enviarlo al padre. -->
		<button @click="$emit('close', name)">Close Popup</button>
		<!-- ejecutamos el emit al hacer click, el cual envia la orden al padre, de pasar la caracteristica showPopup: true, a falsa y hacer desaparecer nuevamente el item. -->
	</div>
</template>

<script>
export default {
	name: 'PopupButton',
	emits: {
		close: (name) => {
			if (!name) {
				return false
			} else {
				return true
			}
		},
		//De esta forma lo que hacemos, es que si el input, va sin nada, salte un error en consola, donde nos dice que la validacion no es correcta, ya que poner el nombre es requerido.
	},
	//Creamos este array emits: ['close'] con el nombre close, siempre tiene que ser un emits, para poder enviar una orden al padre.
	data() {
		return {
			name: '',
			//Creamos la data name, que es la que vamos a enviar al padre.
		}
	},
}
</script>

<style scoped></style>
