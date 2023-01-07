<script setup>
//en el import taskitem lo que hacemos es llamar al componente, para extraer las tareas y asi recorrerlas y mostrarlas en pantalla con el vfor.
import TaskItem from './TaskItem.vue'
import { defineProps } from 'vue'

//De esta forma lo que hacemos es llamar a la variable que crearmos en app.vue pero esta es la que recibe las tareas y las guarda
//en un array, osea las almacena a todas.

defineProps({
	items: {
		type: Array,
		required: true,
	},
})
</script>

<template>
	<ul>
		<TaskItem v-for="task in items" :key="task" :item="task" />
		<!-- En el v-for, lo que vemos en como recorre nuestro array de task y los lleva a items, que ahi es donde se almacenan todas -->
		<!-- las tareas que vayamos agregando para luego mostrarlas. -->
	</ul>
</template>
