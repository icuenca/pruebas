<template>
  <ul class='list-group'>
    <li v-for='(t, indice) in tareas' class='list-group-item' v-bind:class='{terminada: t.terminada}'>
      {{ t.texto }}
      <span class='pull-right'>
        <button type='button' class='btn btn-success btn-xs glyphicon glyphicon-ok' v-on:click="t.terminada=!t.terminada"></button>
        <button type='button' class='btn btn-danger btn-xs glyphicon glyphicon-remove' v-on:click="borrar(indice)"></button>
      </span>
    </li>
  </ul>
</template>

<script>
export default {
  props:['tareas'],
  methods:{
    borrar(indice){
        this.tareas.splice(indice,1)
    }
  }
}
</script>
<!--SE aagrega scope para indicar que el estilo solo aplica a este componente-->
<style scope>
  .terminada
  {
    color:gray;
    text-decoration:line-through;
  }
</style>
