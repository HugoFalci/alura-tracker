<template>
  <header>
      <h1>
          <img src="../assets/imobia_contor.png" alt="" class="logo">
      </h1>
  </header>
</template>


<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
  name: 'BarraLateral'
})
</script>


<style scoped>
header {
  background: #202123;
  width: 100%;
  height: 100vh;
}

@media only screen and (max-width: 768px) {
  header {
    padding: 2.5rem;
    height: auto;
  }
}

.logo {
  width: 90%;
  transform: translateY(-20%);
}
</style>
