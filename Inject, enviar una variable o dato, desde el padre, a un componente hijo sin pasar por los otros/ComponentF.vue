<template>
	<h2>Component F</h2>
	<h3>Component F username {{ username }}</h3>
</template>

<script>
export default {
	name: 'ComponentF',
	inject: ['username'],
	//Dato recibido a traves del comando inject, el cual es llamado directamente de el padre, sin pasar por el resto de componentes.
}
</script>

<style scoped></style>
