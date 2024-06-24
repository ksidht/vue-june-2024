<script setup>
  import { ref, watchEffect } from "vue";
  const count = defineModel('count')
  const title = defineModel('title')
  const props = defineProps(['modalValue'])
  const emit = defineEmits(['update:modelValue'])
  // const API_URL = 'http://localhost:8000'
  const API_URL = 'https://dev-india-company-admin-api.gpssapp.com'

  console.log(props)
  

  function update() {
    count.value++
    console.log(count)
  }

  function updateSecond() {
    title.value++
  }

  watchEffect(async () => {
  // this effect will run immediately and then
  // re-run whenever currentBranch.value changes
  const url = `${API_URL}/api/user/get-user-id`
  const data = await (await fetch(url, {
      method: "POST", // or 'PUT'
      headers: {
        "Content-Type": "application/json",
      },
    })).json()

  console.log(data)
})  

</script>
<template>
  <input />
  <div>VMODEL {{ count }}</div>

  <div>VMODEL CUstomise {{ props.modalValue }}</div> 
  <button  @click="update">v click</button>

  <button  @click="updateSecond">Update second</button>
</template>