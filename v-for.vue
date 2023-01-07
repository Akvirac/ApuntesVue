<template>
	<h2 v-for="(name, index) in names" :key="name">{{ index }} {{ name }}</h2>
	<!-- aca podemos ver que estamos mostrando el array names, el cual recorremos con un vfor, donde name es el seudonimo que se le da a cada uno de los objetos de names, para ir mostrandolo, entonces, el vfor lo recorre segun la cantidad de nombres que contenga names, y cada recorrido, name tiene un valor diferente que va mostrando en pantalla. debemos agregar un key a cada valor para poder ejecturarlo, como en este caso, los nombres son diferentes, podemos utilizarlo como key, en otros casos que sean iguales, no podremos. -->
	<!-- en caso de que querramos ver la posicion de cada nombre, lo que hacemos, es poner la variable index dentro de parentesis junto con name, para ir mostrando cada nombre, junto con su posicion. -->
	<h2 v-for="name in fullNames" :key="name.first">
		{{ name.first }} {{ name.last }}
	</h2>
	<!-- En esta ocacion, lo que hacemos, es crear un array que tiene 2 componentes cada nombre, fullNames, que tiene primero y ultimo, de esta forma, para poder recorrerlo, hacemos lo mismo, names in full names en nuestro vfor, pero a la hora de mostrarlo, lo que hacemos es utilizar, name.first para el primero y name.last para el ultimo, de esta forma queda perfecto. -->
	<div v-for="actor in actors" :key="actor.name">
		<h2>{{ actor.name }}</h2>
		<h3 v-for="movie in actor.movies" :key="movie">{{ movie }}</h3>
		<!-- aca lo que podemos ver, es que estamos haciendo un for sobre otro for, en donde el primer for, recorre el actor, para luego recorrer el siguiente que contiene las peliculas, de esta forma, primer entra el actor, y el for siguiente recorre y muestra cada una de las pelis contenidas en el array, una vez terminada esa lista, pasa al siguiente actor para recorrer las peliculas de ese array. -->
	</div>
	<h2 v-for="(value, key, index) in myInfo" :key="value">
		{{ index }} {{ key }} {{ value }}
	</h2>
	<!-- de esta forma, lo que hacemos, es un for que recorra un objeto, que contiene diferentes variables, en este caso, value en myInfo, para tambien, mostrar, tanto su index, como el nombre de la variable que seria la key. Prestar atencion a como las muestra con llaves y como recorre el for, (value, key, index) in miInfo -->
	<template v-for="name in names" :key="name">
		<!-- hay que tener en cuenta de siempre agregar el key a cada item que llamemos con nuestro for, para que a la pagina, le sea mucho mas facil identificar cada elemento que va asigando cada valor, por ende nos ahorramos muchos errores y facilitamos nuestro trabajo. hay que tener en cuenta como manejar bien ese valor, ya que si tenemos una lista que no repite ningun valor, podemos utilizar el mismo item como key, pero si hay valores iguales en una misma lista, ahi es donde podemos cometer errores. -->
		<h2>{{ name }}</h2>
		<hr />
	</template>
	<!-- de esta forma, lo que hacemos, es hacer varios template, con un v-for, donde cada uno contenga un name, de los names contenidos. puede servir para duplicar un template las veces que nos haga falta. -->
	<template>
		<template v-for="name in names" :key="name">
			<h2 v-if="name === 'Bruce'">{{ name }}</h2>
		</template>
	</template>
	<!-- De esta forma, al saber que elementos contiene nuestro array, podemos llamar a uno en particular, o hacer que lo recorra y si algun elemento es igual a nuestro if, lo va a mostrar, en caso contrario no lo hace. En este caso utilizamos el template, para poder solucionarlo, pero lo ideal seria utilizar una computed property. Pero esta bueno poder ver este modo. -->
</template>

<script>
export default {
	name: 'App',
	data() {
		return {
			names: ['Bruce', 'Clark', 'Diana', 'Pedro', 'Pablo'],
			fullNames: [
				{ first: 'Bruce', last: 'Wayne' },
				{ first: 'Clark', last: 'Kent' },
				{ first: 'Princess', last: 'Diana' },
			],
			actors: [
				{
					name: 'Christian Bale',
					movies: ['Batman', 'The Prestige'],
				},
				{
					name: 'Di caprio',
					movies: ['Titanic', 'Inception'],
				},
			],
			myInfo: {
				name: 'Vishwas',
				channel: 'Codevolution',
				course: 'Vue',
			},
		}
	},
}
</script>

<style>
#app {
	font-family: Avenir, Helvetica, Arial, sans-serif;
	-webkit-font-smoothing: antialiased;
	-moz-osx-font-smoothing: grayscale;
	text-align: center;
	color: #2c3e50;
	margin-top: 60px;
}
.underline {
	text-decoration: underline;
}
.promoted {
	font-style: italic;
}
.new {
	color: green;
}
.sold-out {
	color: red;
}
</style>
