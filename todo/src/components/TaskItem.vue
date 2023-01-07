<script setup>
//import ActionButton from './ActionButton.vue'
import { defineProps } from 'vue'

//en este defineProps, lo que hacemos es recibir la tarea individualmente, para luego ir almacenandolas
//pero eso ya se hace desde TaskList si no me equivoco.

defineProps({
	item: {
		type: String,
		required: true,
	},
})
</script>

<template>
	<div>
		<li class="border-b-2 border-gray-300 px-4 mb-5">{{ item }}</li>
	</div>
</template>
