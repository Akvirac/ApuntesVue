<template>
	<h2>{{ 2 + 3 + 5 }}</h2>
	<!-- aca vemos como dentro de nuestras llaves podemos resolver problemas matematicos, pero es bastante poco practico y dificil de mantener. -->
	<h2>Add method - {{ add() }}</h2>
	<!-- de esta forma, creamos un metodo, que nos permite realizar una suma directamente desde nuestro metodo y mostrarla. -->
	<h2>Add method - {{ add(8, 9, 18) }}</h2>
	<!-- de esta forma, lo que hacemos, es darle un valor a cada variable que tenemos en nuestro metodo, A B C, para luego, proceder a darle los valores correspondientes y sumarlos o realizar la operacion que el metodo pida hacer. -->
	<h2>Multipl method - {{ multiply(baseValue) }}</h2>
</template>

<script>
export default {
	name: 'App',
	data() {
		return {
			baseMultiplier: 5,
			baseValue: 2,
		}
	},
	// lo metodos siempre se encuentran despues de la coma en el primer return, aca lo creamos para luego mostrarlo en nuestro html template
	methods: {
		add(a, b, c) {
			return a + b + c
		},
		multiply(num) {
			return num * this.baseMultiplier
			// siempre tener en cuenta que si nosotros llamamos a algo que se encuentra en data, lo que hacemos es llamarlo con this. y el nombre que le corresponda.
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
