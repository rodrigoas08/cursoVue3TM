<template>
	<div>
		<h1 :class="{ title: true, 'title-home': isHome }">Curso Vue 3</h1>
		<p :class="pClass">
			Lorem ipsum dolor sit amet consectetur adipisicing elit. Aliquid eaque
			voluptatum quis minima pariatur amet asperiores, impedit magnam ab quidem
			obcaecati! Sed alias maiores repudiandae cum aperiam. Ipsam, obcaecati
			doloremque?
		</p>
		<p :style="styleClass">
			Lorem ipsum, dolor sit amet consectetur adipisicing elit. Veritatis nihil,
			culpa quae consequuntur nam ex odit exercitationem sed ullam cupiditate
			velit sapiente consequatur officia vero enim similique id consectetur ad?
		</p>
		<!-- v-bind pode ser substituido pelo ":". Ex: v-bind:key = :key -->
		<div v-for="(obj, index) in todos" :key="obj.id" class="todo-item">
			{{ index + 1 }} - {{ obj.title }}
			<!-- esta img só irá exibir caso obj.imgSrc for true -->
			<img
				class="todo-img"
				v-if="obj.imgSrc"
				:src="obj.imgSrc"
				:alt="obj.imgAlt"
			/>
		</div>
	</div>
</template>

<script>
export default {
	name: "App",
	//data é a central de variáveis do componente, tudo que declarar aqui ficará disponível pra usar no componente
	data() {
		return {
			isHome: true,
			classVar: "",
			pClass: ["text", { "text-home": this.isHome }],
			styleClass: { color: "aqua", background: "black" },
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
.title {
	font-size: 20px;
	color: blue;
}
.title-home {
	font-size: 40px;
	color: green;
}
.text {
	color: gray;
}
.text-home {
	color: greenyellow;
}
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
