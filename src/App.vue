<template>
  <div id="app" class="container">
    <div class="jumbotron">
    <titulo :titulo='titulo'></titulo>
      <!--<h2>{{ titulo }}</h2>-->
    <nueva_tarea :tareas='tareas' v-on:incrementarContador='numTareas += $event'></nueva_tarea>
    <listatareas :tareas='tareas'></listatareas>
    {{ numTareas }}
    </div>
  </div>
</template>

<script>
import titulo from './tituloComponent.vue'
import nueva_tarea from './nuevaTareaComponent.vue'
import listatareas from './listaTareasComponent.vue'
export default {
  components: 
  {
    titulo,
    nueva_tarea,
    listatareas
  },
  data(){
    return{
      titulo :'Lista de Tareas',
      numTareas: 3,
      tareas:[
      {
          texto:'Aprender Vuejs',
          terminada:false
      },
      {
          texto:'Aprender Angular 2',
          terminada:false
      },
      {
          texto:'Aprender Ionic 2',
          terminada:false
      }
     ]
    } 
  }
}
</script>

<style>
</style>
