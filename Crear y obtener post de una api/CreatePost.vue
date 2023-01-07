<template>
	<div>
		<!-- Creamos el form donde vamos a crear un item nuevo para la lista a la cual estabamos llamando previamente. -->
		<form @submit.prevent="createPost">
			<div>
				<label for="userId">Post user ID</label>
				<input type="text" id="userId" v-model="formData.userId" />
			</div>
			<div>
				<label for="title">Post Title</label>
				<input type="text" id="title" v-model="formData.title" />
			</div>
			<div>
				<label for="body">Post body</label>
				<input type="text" id="body" v-model="formData.body" />
			</div>
			<button>Create Post</button>
		</form>
	</div>
</template>

<script>
import axios from 'axios'
export default {
	name: 'CreatePost',
	data() {
		return {
			formData: {
				userId: '',
				title: '',
				body: '',
			},
		}
	},
	methods: {
		//Creamos un metodo, createPost, donde le damos una url y subimos la informacion que nosotros carguemos en nuestro for.
		createPost() {
			axios
				.post('https://jsonplaceholder.typicode.com/posts', this.formData)
				//Mostramos que la informacion se envio correctamente.
				.then((response) => console.log(response))
				//Si la informacion no se envia correctamente, saltaria un error en la consola.
				.catch((error) => console.log(error))
		},
	},
}
</script>

<style scoped></style>
