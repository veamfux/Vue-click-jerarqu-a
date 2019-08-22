<template>
	<h2>{{ titulo }} : {{ NumCurso }}</h2>
</template>

<script>
import { bus } from './../main.js'

export default {
	props:['titulo'],
	data(){
		return{
			NumCurso:0
		}
	},
	mounted (){
		bus.$on('actualizarContador',(NumCurso)=> {
			this.NumCurso = NumCurso;
		})
	}
}
</script>