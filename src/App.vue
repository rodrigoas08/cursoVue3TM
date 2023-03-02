<template>
	<div>
		<div>
			two-way data binding <br />
			v-model -> formulários
		</div>

		<br /><br />

		<label>Nome</label><br />
		<input v-model="name" id="name" type="text" /><br />
		<p class="text-value">{{ name }}</p>

		<br /><br />

		<label>Esportes</label><br />
		<select v-model="esportes">
			<option value="">Escolha seu esporte favorito</option>
			<option value="Futebol">Futebol</option>
			<option value="Vôlei">Vôlei</option>
			<option value="Basquete">Basquete</option>
		</select>
		<br />
		<p class="text-value">{{ esportes }}</p>

		<br /><br />

		<label>Newsletter</label><br />
		<input type="radio" v-model="newsletter" value="Sim" /> Sim

		<input type="radio" v-model="newsletter" value="Não" /> Não
		<br />
		<p class="text-value">{{ newsletter }}</p>

		<br /><br />

		<label>Contrato</label><br />
		<input type="checkbox" v-model="contrato" /> Aceitar nossos termos...

		<br />
		<p class="text-value">{{ contrato }}</p>

		<br /><br />

		<label>Escolha sua cor favorita</label><br />
		<input type="checkbox" v-model="cores" value="Amarelo" /> Amarelo
		<input type="checkbox" v-model="cores" value="Azul" /> Azul
		<input type="checkbox" v-model="cores" value="Verde" /> Verde
		<input type="checkbox" v-model="cores" value="Vermelho" /> Vermelho

		<br />
		<p class="text-value">{{ cores }}</p>
	</div>
</template>

<script>
export default {
	name: "App",
	//data é a central de variáveis do componente, tudo que declarar aqui ficará disponível pra usar no componente
	data() {
		return {
			name: "Rodrigo",
			esportes: "",
			newsletter: "Sim",
			contrato: false,
			cores: [],
		};
	},
};
</script>

<style>
.text-value {
	display: inline;
	margin: 0;
	padding: 0;
	color: red;
}
#app {
	font-family: Avenir, Helvetica, Arial, sans-serif;
	-webkit-font-smoothing: antialiased;
	-moz-osx-font-smoothing: grayscale;
	color: #2c3e50;
	margin: 60px;
}
</style>
