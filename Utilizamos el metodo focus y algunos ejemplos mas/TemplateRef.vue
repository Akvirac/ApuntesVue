<!-- Vamos a crear un input, el cual, va a estar señalado ni bien se cargue la pagina. -->
<template>
	<div>
		<!-- Creamos el input y le damos un type text, podria ser cualquiera y luego le damos el atributo ref donde atribuimos un nombre. -->
		<input type="text" ref="inputRef" />
		<!-- en este componente lo que hacemos es volver a utilizar el ref, para mostrar como pide directamente los datos, ni bien carga la pagina. -->
		<PostList ref="postListRef" />
	</div>
</template>

<script>
//Aca importamos un componente dentro de otro componente, tener en cuenta, que si estamos en la misma carpeta, no hace falta poner ./components, si no directamente ./componente que sea.
import PostList from './PostList'
export default {
	components: {
		PostList,
	},
	name: 'TemplateRef',
	//Finalmente, creamos un metodo mounted() en el cual señalamos que vamos a utilizar ref, su nombre y que hacer con la misma, en ese caso, focusearla cuando se cargue la pagina.
	mounted() {
		//simplemente hacemos que la consola logue la carga que tiene esa referencia, en este caso la lista de 100 posts.
		console.log(this.$refs.postListRef)
		this.$refs.inputRef.focus()
	},
}
</script>

<style scoped></style>
