<template>
	<!-- Creamos el HTML para nuestro input. -->
	<div>
		<!-- Le damos las caracteristicas necesarias para poder enviarle la info a el padre, cuando el usuario escriba. -->
		<input
			type="text"
			:value="modelValue"
			@input="$emit('update:modelValue', $event.target.value)"
		/>
		<!-- type text es el estilo de input que creamos.
         -->
		<!-- :value lo utilizamos para enlazar con el tipo de dato que vamos a enviar, en este caso, un String -->
		<!-- @input="$emit" es para enviar la informacion a nuestro padre a traves del input a data en app.vue. -->
		<!-- con el $event.target.value, lo que hacemos es decirle que envie el valor que tiene el input en ese momento. -->
		<!-- Basicamente lo que hace este input, es, guardar la variable aca en modelValue, para luego, enviarla a el v-model a traves del $emit para que la reciba en nuestro component en la app.vue, para una vez recibido ahi, almacenarlo en "name" que es a la variable que igualamos el v-model.-->
	</div>
</template>

<script>
export default {
	name: 'InputComponent',
	props: {
		//Simplemente avisamos que tipo de dato vamos a enviar.
		modelValue: String,
	},
}
</script>

<style scoped>
input[type='text'] {
	display: block;
	width: 400px;
	padding: 6px 12px;
	font-size: 14px;
	line-height: 1.4;
	color: #555;
	background-color: #fff;
	background-image: none;
	border: 1px solid #ccc;
	border-radius: 4px;
}
</style>
