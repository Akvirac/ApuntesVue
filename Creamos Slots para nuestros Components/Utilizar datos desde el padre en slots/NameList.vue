<template>
	<div>
		<!-- utilizamos un v-for para recorrer el array de nombres que tenemos. -->
		<h3 v-for="name in names" :key="name.firstName">
			<slot :firstName="name.firstName" :lastName="name.lastName"></slot>
			<!-- Dentro creamos el slot, donde le decimos que llame a las variables obtenidas en nuestro v-for en cada ciclo realizado, de esta form las vamos obteniendo y almacenando en las directivas de vue para enviarlas a app.vue el cual se encarga de ir mostrandolas en pantalla. -->
		</h3>
	</div>
</template>

<script>
export default {
	name: 'NameList',
	data() {
		return {
			//Creamos el objeto con el array que contiene los nombres que vamos a utilizar.
			names: [
				{
					firstName: 'bruce',
					lastName: 'wayne',
				},
				{
					firstName: 'clark',
					lastName: 'kent',
				},
				{
					firstName: 'princes',
					lastName: 'diana',
				},
			],
		}
	},
}
</script>

<style scoped></style>
