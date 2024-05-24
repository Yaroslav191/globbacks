<script setup>
import { ref, watch } from 'vue'
const inputText = ref('')
const emit = defineEmits(['update:modelValue'])

const emitInputValue = () => {
  emit('update:modelValue', inputText.value)
}
</script>

<template>
  <div class="search__inner">
    <input v-model="inputText" @input="emitInputValue" class="search-input" type="text" />
    <img class="search-img" src="../assets/search.svg" alt="Search" />
  </div>
</template>

<style>
.search__inner {
  height: 48px;
  position: relative;
  border: 1px solid #d4defe;
  border-radius: 24px;
  margin-bottom: 32px;
}
.search-img {
  position: absolute;
  top: 50%;
  transform: translateY(-50%);
  right: 24px;
}
.search-input {
  width: 100%;
  height: 100%;
  outline: none;
  border: none;
  padding-left: 10px;
}
</style>
