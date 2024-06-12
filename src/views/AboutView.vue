<script setup>
import { ref } from "vue";

import VmodelComponent  from "../components/VmodelComponent.vue";
import VmodelCustomiseComponent from "../components/VModelCustomiseComponent.vue";

const count = ref(12)
const newCount = ref(10)

const modelCount = ref(20)

console.log(count)
console.log(newCount)


</script>
<template>
  <div class="about">

    <h1>This is an about page {{ count }}</h1>
    <h2>New Count {{ newCount }}</h2>
    <VmodelComponent 
      v-model:count="count" 
      v-model:title="newCount"

      :modalValue="modelCount"
      @update:modalValue="$event => (modelCount == $event)"
    ></VmodelComponent>
    
    <br />

    <h2>Modal CUstomise {{ modelCount }}</h2>

    <VmodelCustomiseComponent
      :sidValue="modelCount"
      @update:sidValue="$event => (modelCount = $event)"    
    >
    </VmodelCustomiseComponent>

  </div>
</template>

<style>
@media (min-width: 1024px) {
  .about {
    min-height: 100vh;
    display: flex;
    align-items: center;
    flex-direction: column;
  }
}
</style>
