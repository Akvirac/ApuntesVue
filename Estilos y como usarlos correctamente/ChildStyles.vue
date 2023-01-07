<template>
	<div>
		<slot></slot>
		<!-- <h4>childstyles componet text</h4> -->
	</div>
</template>

<script>
export default {
	name: 'ChildStyles',
}
</script>
<!-- utilizamos el scope para que el estilo se aplique solo al HTML que se encuentra en esta pagina. Hay que tener en cuenta que si no se encuentra dentro de un div, el formato que va a quedar es el de el padre. -->
<!-- LEER SOBRE CSS MODULES. -->
<style scoped>
h4 {
	color: olivedrab;
}
</style>
