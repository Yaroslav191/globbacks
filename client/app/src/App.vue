<script setup>
import Modal from './components/Modal.vue'
import SearchInput from './components/SearchInput.vue'
import Card from './components/Card.vue'
import { ref, onMounted } from 'vue'
import axios from 'axios'

const isShown = ref(false)
const users = ref([])
const inputValue = ''
const userData = ref({
  name: '',
  phone: '',
  email: '',
  address: '',
  position_name: '',
  department: '',
  hire_date: ''
})

onMounted(async () => {
  try {
    const { data } = await axios.get('http://127.0.0.1:3000/')
    users.value = data
  } catch (error) {
    console.log(error)
  }
})

const onCardClick = (user) => {
  isShown.value = true
  userData.value = user
}

const search = (value) => {
  axios
    .get(`http://127.0.0.1:3000?term=${value}`)
    .then((data) => {
      users.value = data.data
    })
    .catch((error) => console.log(error))
}
</script>

<template>
  <div class="container">
    <SearchInput @update:modelValue="search" />
    <Modal :is-shown="isShown" @closeModal="isShown = false" :user="userData" />
    <div class="card__inner">
      <Card v-for="user in users" :key="user.name" :user="user" @click="onCardClick(user)" />
    </div>
  </div>
</template>

<style scoped>
.container {
  padding-top: 64px;
  width: 1120px;
  margin: 0 auto;
}
.card__inner {
  display: grid;
  grid-template-columns: 357px 357px 357px;
  gap: 25px;
}
</style>
