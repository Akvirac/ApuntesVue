<script setup>
//preguntarle a deiv, para que se importa "defineProps" por lo que yo entiendo es para poder llamar o darle caracteristicas a una variable
//creada en la pagina principal, el padre de todos.

import { defineProps } from 'vue'

//podemos ver que a modelValue, le da las propiedades de ser string y que sea requerido, en caso de que no pongan nada, no enviar algo que sea vacio.

defineProps({
	modelValue: {
		type: String,
		required: true,
	},
})
</script>

<template>
	<div>
		<input
			:value="modelValue"
			@input="$emit('update:modelValue', $event.target.value)"
			class="rounded text-center px-2 my-3 border-solid border-2 border-gray-400"
			placeholder="Define Task"
		/>
	</div>
</template>
