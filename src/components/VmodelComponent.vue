<script setup>
  import { ref } from "vue";
  const count = defineModel('count')
  const title = defineModel('title')
  const props = defineProps(['modalValue'])
  const emit = defineEmits(['update:modelValue'])


  console.log(props)
  

  function update() {
    count.value++
    console.log(count)
  }

  function updateSecond() {
    title.value++
  }

</script>
<template>
  <input />
  <div>VMODEL {{ count }}</div>

  <div>VMODEL CUstomise {{ props.modalValue }}</div> 
  <button  @click="update">v click</button>

  <button  @click="updateSecond">Update second</button>
</template>