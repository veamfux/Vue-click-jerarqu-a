<template>
<div class="container" id="app">
  <Titulo :titulo="titulo"></Titulo>
  <Registro :cursos="cursos" :actualizarContador="actualizarContador"></Registro>
  <div class="row">
    <listado v-for="(curso, index) in cursos" :cursos="cursos" :curso="curso" :index="index" :decremento="decremento"></listado>
  </div>
</div>
</template>

<script>
/*exportacion de template*/
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
              { titulo:'curso #3' }
            ],
      NuevoCurso:''
    }
  },
  methods:{
    actualizarContador(){
      this.NumCurso++;
    },
    decremento(){
      this.NumCurso--;
    }
  }
}
</script>

<style>
</style>
