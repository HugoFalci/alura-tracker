<template>
    <header>
        <h1>
            <img src="../assets/logo.png" alt="" class="logo">
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
  padding: 1rem;
  background: #F0F0F0;
  height: 25vw;
  height: 100vh;
  display: inline-block;
}
@media only screen and (max-width: 768px) {
  header {
    padding: 2.5rem;
    height: auto;
  }
}
.logo{
    width: 50px;
    height: auto;
}
</style>