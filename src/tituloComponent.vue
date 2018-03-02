<template>
  <h2>{{ tituloMayusculas() }}</h2>
</template>

<script>
export default {
  props:{
  	titulo:{
  		type: String,
  	 	default: 'Tareas'
  	}
  },
  methods: {
   tituloMayusculas(){
   		return this.titulo.toUpperCase();
   }
  }
}
</script>

<style>
</style>
