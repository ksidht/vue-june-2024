<script setup>
  import { ref } from "vue";

  const props = defineProps(['sidValue'])
  const emit = defineEmits(['update:sidValue'])


  console.log(props)

  

  function update() {
    const newValue = props.sidValue + 1
    console.log(newValue)
    emit("update:sidValue", newValue)
  }


</script>
<template>
  <br />
  <br/>
  <div>VMODEL CUstomise{{ props.sidValue }}</div>
  <button  @click="update">v click</button>

</template>