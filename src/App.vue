<template>
<div class="container" id="app">
  <Titulo :titulo="titulo" :actualizarContador="actualizarContador"></Titulo>
  <Registro :actualizarContador="actualizarContador" :cursos="cursos"></Registro>
  <div class="row">
    <listado v-for="(curso, index) in cursos" :curso="curso" :index="index" :decremento="decremento"></listado>
  </div>
</div>
</template>

<script>
/*exportacion de template*/
import { bus } from './main.js'

import Titulo from './components/TituloComponent.vue'
import Registro from './components/NuevaTareaComponent.vue'
import Listado from './components/ListadoComponent.vue'

export default {
  components: {
    Titulo,
    Registro,
    Listado
  },
  data () {
    return {
      titulo:'Lista de cursos',
      cursos:
            [
              { titulo:'curso #1' },
              { titulo:'curso #2' },
              { titulo:'curso #3' },
              { titulo:'curso #4' },
              { titulo:'curso #5' },
              { titulo:'curso #6' }
            ],
            NuevoCurso:''
    }
  },
  methods:{
    actualizarContador(){
      this.cursos;
      this.NumCurso++;
    },
    decremento(index){
      var curso = this.cursos;
      curso.splice(index,1);
      this.NumCurso--;
      bus.$emit('actualizarContador',this.cursos.length)
    }
  },
  mounted(){
    bus.$emit('actualizarContador',this.cursos.length)
  },
  updated(){
    console.log('Se a actualizado el contador');
  }
}
</script>

<style>
</style>
