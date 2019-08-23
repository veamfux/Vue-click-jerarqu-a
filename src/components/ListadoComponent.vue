<template>

<div class="col-lg-12 col-md-6 pt-2 mt-2">
	<div class="card">
		<div class="card-body">
			<h5 class="card-title">{{ curso.titulo }}</h5>
			<p class="card-text">Lorem ipsum dolor sit amet, consectetur adipisicing elit. Vitae eaque, aliquam assumenda at repudiandae, maxime est necessitatibus doloremque. Iure voluptatem perferendis illo eligendi quas sunt adipisci fugit beatae magnam temporibus.</p>
			<button class="btn btn-danger fas fa-trash-alt" @click="decremento(index);"></button>
		</div>
	</div>
</div>

</template>


<script>
	import { bus } from './../main.js'

	export default{
		props: ['curso','index','decremento'],
		destroyed(){
			console.log('se a eliminado un curso');
		}
	}
</script>