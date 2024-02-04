<script setup lang="ts">
import {  ref, type Ref} from  "vue";
const counter:Ref<number> = ref(0);

const suma = () => {
  counter.value++
}
</script>

<template>
  <h2>Mi sitio web </h2>
  <div class="container">
    <h2>Counter {{ counter }}</h2>
    <button @click="suma()">Suma</button>
  </div>
</template>


<style scoped>
.container {
  width: 600px;
  height: 400px;
  margin: 0 auto;
}
 

</style>