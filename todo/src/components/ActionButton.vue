<script setup></script>

<template>
	<div class="inline">
		<button
			class="text-center px-2 my-3 bg-cyan-700 text-stone-50 rounded mb-10"
		>
			<slot />
			<!-- Lo que hace este tag, es permitir que en nustra app.vue, dentro del boton, podamos asignarle un texto para
            que contenga. -->
		</button>
	</div>
</template>
