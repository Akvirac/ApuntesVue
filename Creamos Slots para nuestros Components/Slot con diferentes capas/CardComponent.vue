<template>
	<div class="card">
		<!-- Como podemos ver, creamos div para cada uno de los slots que vamos a necesitar, en este caso 3, dandoles sus respectivos nombres, tener en cuenta que puede haber un default automatico, el cual en este caso es el card-content. los id son para darle estilos a cada uno. -->
		<div id="card-header"></div>
		<slot name="header"></slot>
		<div id="card-content"></div>
		<slot></slot>
		<div id="card-footer"></div>
		<slot name="footer"></slot>
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
