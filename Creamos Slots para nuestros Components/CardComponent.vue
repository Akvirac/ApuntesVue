<template>
	<!-- Como podemos ver, le damos el estilo card a nuestro div y dentro le colocamos el tag slot, eso nos habilita a realizar los cambios en app.vue. -->
	<div class="card">
		<slot>Default Content</slot>
		<!-- Como podemos ver, tambien le podemos dar un default content, lo que seria algo base en caso de no recibir ninguna informacion de la app.vue el contenido sera el asignado por el componente. -->
	</div>
</template>

<script>
export default {
	//avisamos que vamos a importar.
	name: 'CardComponent',
}
</script>

<style scoped>
/* Estilamos un poco nuestras tarjetas, para darle un poco mas de contenido */
.card {
	box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2);
	transition: 0.3s;
	padding: 16px;
	margin-bottom: 20px;
	width: 200px;
}
.card:over {
	box-shadow: 0 8px 16px 0 rgba(0, 0, 0, 0.2);
}
</style>
