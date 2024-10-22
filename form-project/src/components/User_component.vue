<script setup>
  import { ref } from 'vue';
  let nomUsuario = ref("");
  let numUsuario = ref("");

  const emit = defineEmits(['enviar'])

  let user = {
    nom:String,
    num:Number
  }

  function enviar(){
    user.nom = nomUsuario
    user.num = numUsuario
    emit('enviar',user)
  }

</script>

<template>
  <div>

    <input type="text" placeholder="Nombre de usuario" v-model="nomUsuario">
    <input type="number" placeholder="Numero de telefono" v-model="numUsuario">
    <button @click="enviar">logearse</button>

  </div>
</template>

<style scoped>

</style>
