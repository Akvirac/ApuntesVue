<script setup>
//por convencion y por funcionamiento de vue3 siempre se organiza de la siguiente forma cada archivo
//script setup, donde van los import, las variables a usar, las funciones y todo el javaScript en ese orden.
//Template, donde va todo el HTML, donde se le asigna el jS que corresponda.

//siempre recordar, por convencion, los import siempre se realizan arriba. en esta ocacion, como es el padre,
//lo que hacemos es importar cada component que vamos a utilizar en nustra app.
import InputField from './components/InputField.vue'
import TaskList from './components/TaskList.vue'
import ActionButton from './components/ActionButton.vue'
import { ref } from 'vue'

//hay que recordar, que las variables siempre se crean en la pagina padre, la cual seria
//la que nosotros montamos toda nuestra app.vue para luego llamarlas desde el componente donde la queremos usar,
//llamandola con el metodo "defineProps()"

const taskName = ref('')
const tasks = ref([])

//Con estas funcion lo que hacemos es pushear lo que se cargue en el inputField, como podemos ver, tiene su @click que seria como
//un listener o un alerta para que cuando ocurra el evento, click o enter, se ejecute la fucion que en este caso es handleSubmit.
//que ella se encarga de pushear un valor a tasks.
//en la siguiente linea lo que hace es resetear el valor de taskName para que en nuestro input no se mantenga la tarea escrita
//esa parte de la funcion es solo estetica, pero es importante.

function handleSubmit() {
	tasks.value.push(taskName.value)
	taskName.value = ''
}
</script>

<template>
	<div class="flex flex-col justify-center items-center">
		<h1 class="font-semibold text-6xl">To Do List</h1>
		<!-- De esta forma estilamos, utilizando el tailwind, el cual lo llamamos e instalamos siguiendo una guia. -->

		<InputField v-model="taskName" @keyup.enter="handleSubmit" />
		<!-- En este imputfield vemos que llamamos con el v-model a taskname y agregamos el evento que desata el handlesubmit */ }} -->
		<ActionButton @click="handleSubmit">Add</ActionButton>
		<!-- Aca agregamos otro evento y tambien, empezamos a darle un nombre particular a cada boton generico entre los tags */ }} -->

		<TaskList :items="tasks" />
	</div>
</template>
