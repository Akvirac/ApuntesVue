<template>
	<!-- en esta seccion vamos a aprender a manejar forms, todo tipo de ellos, capturar inputs, inputs, textareas, y enviarlas a nuestros datos de informacion y poder aplicarle methods etc. -->
	<div>
		<pre>
            {{ JSON.stringify(formValues, null, 2) }}
        </pre
		>
		<!-- de esta forma vemos que el form que estamos usando esta enviando el dato correspondiente. -->
	</div>
	<form @submit="submitForm">
		<div>
			<label for="name">Name</label>
			<input type="text" id="name" v-model="formValues.name" />
			<!-- aca lo que hacemos es crear un form, donde cargamos un nombre, el cual con el vmodel, enviamos a una caracteristica de nuestro objeto formValues, de esta forma vamos captando informacion. -->
		</div>
		<div>
			<label for="profile">Profile Summary</label>
			<textarea id="profile" v-model="formValues.profileSumary"></textarea>
			<!-- en este div, aplicamos lo mismo que en el anterior, creamos un text area donde guardamos la informacion que el usuario cargue en el mismo, para almacenarla en nuestro formValues.profileSumary. -->
		</div>
		<div>
			<label for="country">Country</label>
			<select id="country" v-model="formValues.country">
				<option value="">Select a Country</option>
				<option value="india">India</option>
				<option value="vietnam">Vietnam</option>
				<option value="singapore">Singapore</option>
			</select>
			<!-- en este div lo que hacemos es crear un select, donde ponemos varias opciones de paises disponibles, para seleccionar uno y el mismo almacenarlo dentro de nuestro objeto, en la variable country. tener en cuenta que el v model lo hacemos directamente en el select, no en las opciones. -->
		</div>
		<div>
			<label for="job-location">Job Location</label>
			<select id="job-location" multiple v-model="formValues.jobLocation">
				<option value="india">India</option>
				<option value="vietnam">Vietnam</option>
				<option value="singapore">Singapore</option>
			</select>
			<!-- de esta forma, lo que hacemos, es crear un dropdown en el que podamos seleccionar varias opciones, haciendo ctr + click en el navegador, el cual nos va almacenando las diferentes opciones dentro de nuestro array "jobLocation".  -->
		</div>
		<div>
			<input
				type="checkbox"
				id="remoteWork"
				v-model="formValues.remoteWork"
				true-value="yes"
				false-value="no"
			/>
			<label for="remoteWork">Open to remote work?</label>
			<!-- en este div, nos dedicamos a preguntarle al usuario si esta abierto a trabajar desde casa o no, para lo cual creamos un input/checkbox, donde le damos la caracteristica de que en lugar de el valor sea false or true, que el valor sea yes or no y lo almacenamos dentro de nuestro objeto en la variable "remoteWork". -->
		</div>
		<div>
			<label>Skill set</label>
			<input
				type="checkbox"
				id="html"
				value="html"
				v-model="formValues.skillSet"
			/>
			<label for="html">HTML</label>
			<input
				type="checkbox"
				id="CSS"
				value="CSS"
				v-model="formValues.skillSet"
			/>
			<label for="css">CSS</label>
			<input
				type="checkbox"
				id="javaScript"
				value="javaScript"
				v-model="formValues.skillSet"
			/>
			<label for="javaScript">javaScript</label>
			<!-- En este div, lo que hacemos es crear un pequeño cuestionario de las habilidades del postulante, donde el puede tildar las opciones en las que este capacitado, las cuales son javaScript, HTML, CSS. Las cuales se almacenan en nuestro array llamado SkillSet dentro de nuestro objeto.  -->
		</div>

		<div>
			<label>Years Of Experience</label>
			<input
				type="radio"
				id="0-2"
				value="0-2"
				v-model="formValues.yearsOfExperience"
			/>
			<label for="html">0-2</label>
			<input
				type="radio"
				id="3-5"
				value="3-5"
				v-model="formValues.yearsOfExperience"
			/>
			<label for="css">3-5</label>
			<input
				type="radio"
				id="6-10"
				value="6-10"
				v-model="formValues.yearsOfExperience"
			/>
			<label for="javaScript">6-10</label>
			<input
				type="radio"
				id="+10"
				value="+10"
				v-model="formValues.yearsOfExperience"
			/>
			<label for="javaScript">+10</label>
		</div>
		<!-- En este div, creamos algo similar al de skillsSet pero solo puede seleccionar uno donde le ofrecemos las opciones de años de experiencia que tiene el usuario. Para almacenarlo en yearsOfExperience dentro de nuestro objeto formValues. -->
		<div>
			<button>Submit</button>
			<!-- En caso de que nosotros estemos haciendo un form, el boton por defecto si no le ponemos ningun type, lo que hace es por iniciativa, enviar nuestro formulario y ejectutar el evento que tenemos arriba en el form, que este caso seria submitForm. -->
		</div>
	</form>
</template>

<script>
export default {
	name: 'App',
	data() {
		return {
			// siempre tengamos en cuenta que aca vamos a ir agregando nuestras variables, en este caso es un solo objeto que contiene varias, formValues contiene name, profileSumary, etc. las cuales las vamos llamando con su nombre, formValues.name en el caso de nombre.
			formValues: {
				name: '',
				profileSumary: '',
				country: '',
				jobLocation: [],
				remoteWork: 'no',
				// siempre que iniciamos alguna variable booleana la seteamos en falso por el echo de que siempre al aparecer destildada la checkbox, seria falso o cualquier nombre que nosotros le pongamos como negativo.
				skillSet: [],
				yearsOfExperience: '',
			},
		}
	},
	methods: {
		submitForm(event) {
			event.preventDefault()
			console.log('form.values', this.formValues)
			// con este metodo lo que hacemos en enviar nuestro form a lo que seria su almacenaje, en este caso solo lo que hacemos es mostrarlo en el console log, pero aqui deberia ir donde lo enviamos realmente.
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
