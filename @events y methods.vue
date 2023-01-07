<template>
	<h2>{{ name }}</h2>
	<div>
		<button @:click="changeName, increment">Change name</button>
		<!-- de esa forma, con el v-on lo que hacemos, es poner un listner en el boton, para que cuando nosotros pasemos el mause por encima, hagamos click o hagamos algo determinado,, en el v-on lo que haga es cambiar el name, a batman. es algo simple pero es para arrancar a hacer pequeños eventos dentro de nuestra pagina. -->
	</div>
	<h2>{{ count }}</h2>
	<div>
		<button @:click="count -= 1">Decrement</button>
		<button @:click="count = 0">Reset</button>
		<button @:click="count += 1">Increment</button>
		<!-- Esto que estamos viendo son in line events, lo que quiere decir que son eventos que suceden en la misma linea donde creamos el elemento en particular, tener en cuenta que creamos un variable count dentro de nuestra data, pero luego la vamos modificando desde nuestros botones. -->
	</div>
	<div>
		<button @:click="decrement">Decrement</button>
		<button @:click="reset">Reset</button>
		<button @:click="increment">Increment</button>
		<button @:click="increment5">Increment 5</button>
		<button @:click="decrement5">Decrement 5</button>
		<!-- De esta forma, hacemos lo mismo que de la otra manera, pero utilizando un metodo que realice la operacion requerida, llamandolo por su nombre, podemos ver que cambia el color a amarillito que es el color de los metodos al llamarlos. -->
	</div>
	<div>
		<button @:click="decrement">Decrement</button>
		<button @:click="reset">Reset</button>
		<button @:click="increment">Increment</button>
	</div>
</template>

<script>
export default {
	name: 'App',
	data() {
		return {
			name: 'Vishwas',
			count: 0,
		}
	},
	methods: {
		changeName() {
			this.name = 'Batman'
		},
		increment() {
			this.count += 1
		},
		decrement() {
			this.count -= 1
		},
		reset() {
			this.count = 0
		},
		increment5() {
			this.count += 5
		},
		decrement5() {
			this.count -= 5
		},
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
