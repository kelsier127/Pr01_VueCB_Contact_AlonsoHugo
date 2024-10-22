<script setup>
  import User_component from "./components/User_component.vue"

  function recibir(user){
    console.log(user.nom.value)
  }
  
</script>

<template>
  <div>
    <h1>Form épico</h1>

    <User_component @enviar="recibir"/>
  </div>
</template>

<style scoped>

</style>
