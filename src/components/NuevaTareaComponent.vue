<template>
	<div class="input-group mb-3">
		<input type="text" class="form-control" v-model="NuevoCurso"  @keyup.enter="agregarcurso()">
		<div class="input-group-prepend">
			<span class="input-group-text fas fa-plus" id="basic-addon1" @click="agregarcurso()"></span>
		</div>
	</div>
</template>


<script>
import { bus } from './../main.js'

export default {
	props:['actualizarContador','cursos'],
		data(){
		return{
			NuevoCurso:''
		}
	},
	methods:{
		agregarcurso(){
			var curso = this.cursos;
			var texto = this.NuevoCurso.trim();
			if(texto){
				curso.push({
					titulo:texto,
				})
				// this.$emit('incrementarContador', 1);
				//this.actualizarContador();
				bus.$emit('actualizarContador',this.cursos.length)
			}
			this.NuevoCurso = '';
		}
	}

}
</script>