<template>

<div class="col-lg-12 col-md-6 pt-2 mt-2">
	<div class="card">
		<div class="card-body">
			<h5 class="card-title">{{ curso.titulo }}</h5>
			<p class="card-text">Lorem ipsum dolor sit amet, consectetur adipisicing elit. Vitae eaque, aliquam assumenda at repudiandae, maxime est necessitatibus doloremque. Iure voluptatem perferendis illo eligendi quas sunt adipisci fugit beatae magnam temporibus.</p>
			<button class="btn btn-danger fas fa-trash-alt" @click="borrar(index);"></button>
		</div>
	</div>
</div>

</template>


<script>
	import { bus } from './../main.js'

	export default{
		props: ['curso','index','cursos','decremento'],
		methods:{
			borrar(index){
				var curso = this.cursos;
				curso.splice(index,1);
				bus.$emit('decremento',this.cursos.length)
			}
		},
		destroyed(){
			bus.$emit('actualizarContador',this.cursos.length)
			console.log('se a eliminado un curso');
		}
	}
</script>