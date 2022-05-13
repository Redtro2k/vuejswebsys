<template>
  <h1>question 1.</h1>
  <p v-for="ref in now" :key="ref" v-text="ref"></p>
  <h1>question 2.</h1>
  <input type="text" v-model="form.input1">
  <input type="text" v-model="form.input2">
  <button @click="showProd(form.input1, form.input2)">Add product</button>
  <h1>question 3.</h1>
  <ul>
    <li v-for="name in newArray" :key="name" v-text="name"></li>
  </ul>
</template>
<script setup>
const { computed, reactive }=require("@vue/runtime-core");

  const form = reactive({
    input1: null,
    input2: null
  })
  function showProd(n1, n2){
    return alert(n1 + ' ' + n2)
  }

  const now = computed(() =>{
    let count = 0
    let repeat = []
    while(count < 5){
      console.log('keep going')
      repeat.push('keep going')
      count++
    }
    alert(repeat)
    return repeat;
  })

  const newArray = computed(() => new Array('Darwin', 'Dar', 'Llacuna'))
</script>

