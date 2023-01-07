<template>
	<h2>Fullname - {{ firstName }} {{ lastName }}</h2>
	<!-- de esta forma, lo que hacemos es concatenar 2 propiedades de nuestra data. -->
	<h2>Computed fullname - {{ fullName }}</h2>
	<!-- Aca lo que estamos haciendo, es utilizar una computed property, para de esta forma, hacer 2 datos separados uno solo. La diferencia fundamental, es que de esta forma, se crea otro data llamada fullName, en cambio, la otra solo concatena 2 datos. Esto es una ventaja debido a que optimiza y es mas facil lectura que concatenar datos. -->
	<button @click="changeFullName">Change full name</button>
	<!-- Con este boton lo que hacemos es cambiar todo el nombre desde un metodo, el proceso lo describo mejor en el mismo metodo. -->
	<h2>
		Total -
		{{ items.reduce((total, curr) => (total = total + curr.price), 0) }}
	</h2>
	<h2>Computed total - {{ total }}</h2>
	<h2>Discount - {{ discount10 }}</h2>
	<h2>Total Final {{ final }}</h2>
	<!-- En estos ultimos 3 h2 lo que vemos, es como podemos utilizar las computed
	propertys, para ahorrar codigo dentro de nuestro HTML, en el primero vemos,
	como llegamos al total, para luego, en el 2do transformamos ese proceso a una
	computed property, el cual llevamos todo ese codigo a nuestra data, para luego
	llamarlo y por ultimo, lo que hacemos es a ese total, sacar un 10% de
	descuento. Como ultimo paso, printeamos el total ya con el descuento incluido. -->
	<button @click="items.push({ id: 4, title: 'Keyboard', price: 50 })">
		Add Item
	</button>
	<!-- Con este ejemplo, lo quea hacemos, es demostrar como las computed propertys lo que hacen, es que al sumar un item mas a nuestro carrito, ya realiza todos los procedimientos automaticamente, el total, el descuento y el total final. Lo cual es un beneficio contra hacer todo el proceso dentro de nuestro html, ya que le quita automatizacion. -->
	<!-- una pregunta que nos podemos hacer es de porque utilizamos una computed property y no un metod en estos casos, el cual nos daria el mismo resultado y la respuesta en muy simple, la gran diferencia entre estos 2 es que el metodo se ejecuta cada vez que se actualiza la pagina, lo cual en vue, es muchisimas veces, en cambio la computed property lo que hace es realizar el calculo solo una vez y se almacena, entonces la pagina al refrescarse, directamente llama a los resultados sin realizar ningun calculo, lo cual implica un ahorro de recursos bastante grande. -->
	<template v-for="item in items" :key="item.id">
		<h2 v-if="item.price > 100">{{ item.title }} {{ item.price }}</h2>
		<!-- En este caso, volvemos a realizar un proceso como ejemplo, dentro de nuestro HTML, lo cual, esta mal, lo ideal es hacerlo con una computed property, lo cual realizaremos a continuacion. -->
		<!-- Tenemos que tener cuidado a la hora de utiliazar un v-for en un template, ya que si realizamos algun proceso dentro, se repetira la cantidad de veces que se recorra el mismo, por ende nos multiplicara el proceso. -->
	</template>
	<h2 v-for="item in expensiveItems" :key="item.id">
		{{ item.title }} {{ item.price }}
		<!-- En de esta forma, utilizamos correctamente una computed property, a la hora de llamar a los items que sean mas caros que 100, hacemos con un v-for recorrer los items que se encuentren en expensiveItems que ya esta realiando la accion de filtrarlos para ir mostrando su titulo y precio. -->
	</h2>
</template>

<script>
export default {
	name: 'App',
	data() {
		return {
			firstName: 'bruce',
			lastName: 'wayne',
			thirdName: ' ',
			items: [
				{
					id: 1,
					title: 'TV',
					price: 100,
				},
				{
					id: 2,
					title: 'Phone',
					price: 200,
				},
				{
					id: 3,
					title: 'Laptop',
					price: 300,
				},
			],
		}
	},
	methods: {
		changeFullName() {
			this.fullName = 'Pedro julian Kent'
			//aca lo que hacemos es cambiar full name a un nombre completamente diferente, el cual se obtiene desde aca y lo guarda en fullName.
		},
	},
	computed: {
		fullName: {
			get() {
				return `${this.firstName} ${this.lastName} ${this.thirdName}`
			},
			set(value) {
				const names = value.split(' ')
				this.firstName = names[0]
				this.lastName = names[1]
				this.thirdName = names[2]
				//En esta computed recibimos el nombre completo desde el metodo, para dividirlo en 3 partes y recorrerlas en nuestro HTML, como podemos ver son 3, los cuales los dividimos en un array con SPLIT, para printearlos en pantalla por posicion.
			},

			// aca sumamos los 2 nombres que tenemos, para hacer un dato nuevo llamado fullName.
		},
		total() {
			return this.items.reduce((total, curr) => (total = total + curr.price), 0)
			// En esta computed lo que hacemos es sumar el total de nuestra compra.
		},
		discount10() {
			return this.total * 0.1
			// Aca lo que hacemos es crear otra computed donde hacemos un 10% de descuento al total.
		},
		final() {
			return this.total - this.discount10
			// Por ultimo en esta, lo que hacemos es restarle el descuento al total principal, para saber cuanto debe abonar el cliente.
		},
		expensiveItems() {
			return this.items.filter((item) => item.price > 100)
			// En esta computed, realizamos un filtro de los items que tinen un precio mayor a 100 para printearlos en nuestro h2.
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
