<template>
	<div>
		<div v-for="(obj, index) in todos" :key="obj.id" class="todo-item">
			{{ index + 1 }} - {{ obj.title }}
		</div>
	</div>
</template>

<script>
import axios from "axios";
export default {
	name: "App",
	//data é a central de variáveis do componente, tudo que declarar aqui ficará disponível pra usar no componente
	// data() {
	// 	return {
	// 		todos: [
	// 			{
	// 				userId: 1,
	// 				id: 1,
	// 				title: "delectus aut autem",
	// 				completed: false,
	// 			},
	// 			{
	// 				userId: 1,
	// 				id: 2,
	// 				title: "quis ut nam facilis et officia qui",
	// 				completed: false,
	// 			},
	// 			{
	// 				userId: 1,
	// 				id: 3,
	// 				title: "fugiat veniam minus",
	// 				completed: false,
	// 			},
	// 			{
	// 				userId: 1,
	// 				id: 4,
	// 				title: "et porro tempora",
	// 				completed: true,
	// 			},
	// 			{
	// 				userId: 1,
	// 				id: 5,
	// 				title:
	// 					"laboriosam mollitia et enim quasi adipisci quia provident illum",
	// 				completed: false,
	// 			},
	// 		],
	// 	};
	// },

	data() {
		return {
			todos: null,
		};
	},

	mounted() {
		axios
			.get("https://jsonplaceholder.typicode.com/todos")
			.then((response) => {
				this.todos = response.data;
			})
			.catch((error) => {
				console.error(error);
			});
	},
};
</script>

<style>
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
