<script setup>
  import { computed,ref,reactive } from 'vue';

  import User_component from "./components/User_component.vue"

  let arrayUsers = reactive([]);
  let filtro = ref("");

  let arrayFiltro = computed(() => 
    arrayUsers.filter(user =>
      user.nombre.includes(filtro.value),
    ),
  )


  function recibir(user){

    let usuario = {
      nombre: user.nom,
      telefono: user.num
    };

    arrayUsers.push(usuario);

    console.log(arrayUsers);

  }
  
</script>

<template>
  <div>
    <h1>Form épico</h1>

    <User_component @enviar="recibir"/>

    <input v-model="filtro">

    <ul>
      <li v-for="usuario in arrayFiltro" :key="usuario">
        {{ usuario.nombre }} - {{ usuario.telefono }}
      </li>
    </ul>
  </div>
</template>

<style scoped>

</style>
