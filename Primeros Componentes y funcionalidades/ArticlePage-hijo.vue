<template>
	<div>
		<h2>Article Component</h2>
		<h2 v-bind="$attrs">{{ title }}</h2>
		<!-- Si nosotros queremos que un tag de HTML, tenga una id, aplicamos el v-bind="$attrs" para poder agregarselo y evitar que lo aplique solo sobre el div, si no tambien sobre el tag en cuestion y en caso de no tener un div, de esta forma se lo aplicamos a un tag de HTML particular.Cabe aclarar que si aplicamos un propiedad abajo, podemos eliminar ese comportamiento de aplicar automaticamente el id al div.-->
		<h2>Likes - {{ likes }}</h2>
		<h2>Published - {{ isPublished ? 'yes' : 'no' }}</h2>
	</div>
</template>

<script>
export default {
	name: 'ArticlePage',
	props: {
		title: {
			//si creamos un objeto con el titulo, podemos agregarle varias caracteristicas al mismo, en este caso, es un String y es required, por ende si borramos el nombre desde nuestro padre, en consola nos saltara que falta un valor requerido.
			type: String,
			required: true,
			default: 'Article default Title',
			//Usando esta caracteristica default, lo que hacemos es que si a el titulo no nos lo pasan desde nuestro padre, se pone por defecto, el que nosotros tengamos como default.
			//Se pueden usar muchos tipos de type en nuestros componentes, aparte de los usados, como arrays, objetos, date y funciones.
		},
		//Con esta props, lo que hacemos, es dejar en claro que es lo que va a recibir nuestro title, en cuanto a tipo de dato, dejando en claro y ayudando a convenciones.
		likes: Number,
		//Siempre recordar que estos tipos de caracteristicas, comienzan con mayuscula a la hora de llamarlas.
		//De esta forma, estamos creando variables, las cuales reciben datos de nuestro padre, pero especificando que tipo de dato son.
		isPublished: Boolean,
		//Por ultimo creamos un valor booleano el cual, es
	},
	inheritAttrs: false,
	//Con esta orden en nuestro script, lo que hacemos, es desabilitar el hecho de que si nosotros agregamos un ID, se lo agregue tambien al div, que contiene el tag al que nosotros queremos nombrar.
}
</script>

<style scoped></style>
