<template>
  <div class='input-group'>
    <input v-model='nueva_tarea' type='text' placeholder="Escribe una nueva tarea" class='form-control' 
    v-on:keyup.enter = 'agregar_tarea'>
    <span class='input-group-btn'>
      <button type='button' v-on:click='agregar_tarea' class='btn btn-primary'>Agregar</button>
    </span>
  </div>
</template>

<script>
export default {
 data(){
  return{
    nueva_tarea: ''
  }
 },
 props:['tareas'],
 methods:{
  agregar_tarea(){
     var texto = this.nueva_tarea.trim();
          if(texto)
          {
              this.tareas.push({
              texto:texto,
              terminada:false
              })
              this.$emit('incrementarContador',1);
          }
          this.nueva_tarea = '';
  }
 }
}
</script>

<style>
</style>
