<!-- En esta pagina, estamos creando nuestro primer componente, hay que tener en cuenta 3 cosas en esta parte. -->
<!-- Crear el componente dentro de components siempre teniendo 2 nombres el mismo, recordar que comienza con mayusculas y la segunda palabra igual. -->
<!-- Crear el template con todo el HTML que contenga el mismo. -->
<!-- Por ultimo, se crea el script donde contiene el export. Donde esta el nombre de el componente que vamos a dejar para exportar. -->

<template>
	<!-- El template que contiene todo el HTML. -->
	<div>
		<h2>Hello {{ name }} Alias {{ heroName }}</h2>
		<!-- Dentro de nuestro HTML, creamos la interpolacion con llaves para ir llamando a esa variable, que agregamos en la App. -->
		<!-- Se pueden hacer concatenaciones como podemos ver, llamar varias variables e ir encadenandolas. -->
	</div>
</template>

<script>
export default {
	// El export creado de la siguiente forma
	name: 'GreetPage',
	props: ['name', 'heroName'],

	//Procedemos a crear un dato llamado props, con el array 'name', donde se almacenan los datos que agregamos en el template de nuestra pagina principal.
	//Tener en cuenta que si agregamos alguna otra propiedad, siempre se va a encontrar dentro de el array props.
	//Siempre recordar que esta pagina es hija de App.Vue.
}
</script>

<style scoped></style>
<!-- Tener en cuenta que con el vscode extension de vue, con vbase-css creamos el esqueleto completo del archivo automaticamente. -->
