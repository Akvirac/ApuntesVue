<template>
	<div>
		<!-- Creamos el boton que va a ejecutar el metodo para llamar a los post. -->
		<button @click="getPost">Load Post</button>
		<!-- Creamos un h3, con el mensaje de error en caso de que no reciba correctamente l informacion. lo hacemos con un v-if para solo se muestre en caso de que erorMsg contenga algo. -->
		<h3 v-if="errorMsg">{{ errorMsg }}</h3>
		<!-- Creamos un div con la directiva v-for, donde recorremos los items que obtenemos al presionar el boton y ejecutar el metodo, para luego postearlos con el h3 y p, tener en cuenta que todo tiene que estar dentro de un solo div, si no la directiva v-for no va a encontrar como ir posteando los items. -->
		<div v-for="post in posts" :key="post.id">
			<h3>{{ post.id }} {{ post.title }}</h3>
			<p>{{ post.body }}</p>
		</div>
		<hr />
	</div>
</template>

<script>
// Importamos la biblioteca de axios, que seria un interlocutor entre los servidores o paginas con nuestra app
import axios from 'axios'

export default {
	name: 'PostList',
	//si utilizamos este metodo, lo que hacemos, es que en la creacion de la pagina, automaticamente, la misma cargue los archivos que antes pediamos con el boton.
	created() {
		this.getPost()
	},
	data() {
		return {
			//Creamos el array donde se van a ingresar los post.
			posts: [],
			errorMsg: '',
		}
	},
	//Creamos un metodo getPost para llamar a la pagina de donde obtenemos los post.
	methods: {
		getPost() {
			//url de los post
			axios
				//con el get llamamos a la pagina o servidor desde donde vamos a obtener la informacion.
				.get('https://jsonplaceholder.typicode.com/posts')
				//.then hace que al desatar el evento genere una respuesta donde nos da la informacion.
				.then((response) => {
					//console.log lo utilizamos para chequear que estamos recibiendo info.
					console.log(response.data)
					//Aca almacenamos toda la info que contiene la url o servidor en nuestro array creado en este caso.
					this.posts = response.data
				})
				//Con el catch respondemos algo a la informacion recibida, en este caso, si la base de datos esta funcionando mal o mal colocada la url, enviamos un mensaje de error al recibir la data.
				.catch((error) => {
					console.log(error)
					this.errorMsg = 'Error retrieving data'
				})
		},
	},
}
</script>

<style scoped></style>
