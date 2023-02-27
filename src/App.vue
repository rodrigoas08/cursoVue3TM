<template>
	<div>
		<!-- v-bind pode ser substituido pelo ":". Ex: v-bind:key = :key -->
		<div v-for="(obj, index) in todos" :key="obj.id" class="todo-item">
			{{ index + 1 }} - {{ obj.title }}
			<!-- esta img só irá exibir caso obj.imgSrc for true -->
			<img class="todo-img" v-if="obj.imgSrc" :src="obj.imgSrc" :alt="obj.imgAlt" />
		</div>
	</div>
</template>

<script>
export default {
	name: "App",
	//data é a central de variáveis do componente, tudo que declarar aqui ficará disponível pra usar no componente
	data() {
		return {
			todos: [
				{
					userId: 1,
					id: 1,
					title: "delectus aut autem",
					completed: false,
					imgSrc: "https://via.placeholder.com/150/3d1365/00ff00/?text=Imagem",
					imgAlt: "Foto do Jon",
				},
				{
					userId: 1,
					id: 2,
					title: "quis ut nam facilis et officia qui",
					completed: false,
					imgSrc: "https://via.placeholder.com/150/3d1365/00ff00/?text=Imagem",
					imgAlt: "Foto do Jon",
				},
				{
					userId: 1,
					id: 3,
					title: "fugiat veniam minus",
					completed: false,
				},
				{
					userId: 1,
					id: 4,
					title: "et porro tempora",
					completed: true,
				},
				{
					userId: 1,
					id: 5,
					title:
						"laboriosam mollitia et enim quasi adipisci quia provident illum",
					completed: false,
				},
			],
		};
	},
};
</script>

<style>
.todo-img {
	display: block;
}
.todo-item {
	background: #00ff00;
	color: #3d1365;
	font-weight: bold;
	margin: 0 0 3px 0;
	padding: 3px 6px;
}
#app {
	font-family: Avenir, Helvetica, Arial, sans-serif;
	-webkit-font-smoothing: antialiased;
	-moz-osx-font-smoothing: grayscale;
	color: #2c3e50;
	margin: 60px;
}
</style>
