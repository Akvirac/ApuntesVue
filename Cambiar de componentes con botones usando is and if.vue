<!-- En este archivo lo que vamos a hacer es cambiar de componentes con un boton, teniendo 3 botones y 3 componentes a donde dirigirnos. -->
<!-- Tener en cuenta que solo con esto se puede cambiar de componentes, en los mismos no hay que hacer nada salvo crearlos. -->
<template>
	<!-- Creamos los 3 botones con el @click para escuchar cuando se haga click en cada uno en particular, dandole el valor a activeTab de cada tab en particular. -->
	<button @click="activeTab = 'TabA'">Tab A</button>
	<button @click="activeTab = 'TabB'">Tab B</button>
	<button @click="activeTab = 'TabC'">Tab C</button>
	<!-- Con este tag lo que hacemos es lo mismo que los if, solo que mucho mas simple y mejor codificado. -->
	<component :is="activeTab" />
	<!-- Conectamos los 3 componentes y creamos un if para cada uno para validar si activeTab tiene valor similar a su nombre, esta se mostrara. -->
	<!-- <TabA v-if="activeTab === 'TabA'" /> -->
	<!-- <TabB v-if="activeTab === 'TabB'" /> -->
	<!-- <TabC v-if="activeTab === 'TabC'" /> -->
	<!-- Como este metodo es particular y la hora de utilizar muchos componentes puede ser muy enredado, vamos a mostrar otro. -->
	<KeepAlive></KeepAlive>
	<!-- Con este tag exclusivo de vue, lo que hacemos es que en caso de estar llenando algun formulario o cualquier tipo de campo que quede y cambiamos de componente, quede guardado, ya que si no estuviera este tag, cada vez que se cambia de comp, lo que sucede es que se reinicia a 0. -->
</template>

<script>
//importamos nuestros componentes.
import TabA from './components/TabA.vue'
import TabB from './components/TabB.vue'
import TabC from './components/TabC.vue'

export default {
	name: 'App',
	components: {
		//Lo añadimos a components.
		TabA,
		TabB,
		TabC,
	},
	data() {
		return {
			//Creamos la variable la cual cambiara segun que boton apretemos, por ende, mostrara cada una de las 3 tabs segun corresponda. En este caso, la inicializamos en TabA.
			activeTab: 'TabA',
		}
	},
	methods: {},
}
</script>

<style scoped>
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
