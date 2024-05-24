<script setup>
const props = defineProps(['isShown', 'user'])
const emit = defineEmits(['closeModal'])

console.log(props.user.name)
</script>

<template>
  <div v-show="isShown" class="modal__overlay">
    <div class="modal__inner">
      <div class="modal__header">
        <div class="modal__title">{{ props.user.name }}</div>
        <div class="modal__close" @click="emit('closeModal')">
          <img src="../assets/cross.svg" alt="Close" />
        </div>
      </div>
      <div class="modal__body">
        <div class="modal__body-item">
          <div class="modal__item-name">Телефон:</div>
          <div class="modal__item-value">{{ props.user.phone }}</div>
        </div>
        <div class="modal__body-item">
          <div class="modal__item-name">Почта:</div>
          <div class="modal__item-value">{{ props.user.email }}</div>
        </div>
        <div class="modal__body-item">
          <div class="modal__item-name">Дата приема:</div>
          <div class="modal__item-value">{{ props.user.hire_date }}</div>
        </div>
        <div class="modal__body-item">
          <div class="modal__item-name">Должность:</div>
          <div class="modal__item-value">{{ props.user.position_name }}</div>
        </div>
        <div class="modal__body-item">
          <div class="modal__item-name">Подразделение:</div>
          <div class="modal__item-value">{{ props.user.department }}</div>
        </div>
      </div>
      <div class="modal__addtion-inner">
        <div class="modal__addtion-title">Дополнительная информация:</div>
        <p class="modal__addtion-text">
          Разработчики используют текст в качестве заполнителя макта страницы. Разработчики
          используют текст в качестве заполнителя макта страницы.
        </p>
      </div>
    </div>
  </div>
</template>

<style scoped>
.modal__addtion-text {
  font-size: 16px;
  line-height: 18px;
  color: #8189a3;
}
.modal__addtion-title {
  color: #262c40;
  font-size: 18px;
  margin-bottom: 12px;
}
.modal__body {
  margin-bottom: 40px;
}
.modal__body-item {
  display: flex;
  /* justify-content: space-between; */
  margin-bottom: 14px;
  align-items: center;
}
.modal__body-item:last-child {
  margin-bottom: 0;
}
.modal__item-value {
  text-align: left;
  color: #8189a3;
  font-size: 16px;
  line-height: 18px;
  flex-grow: 1;
}
.modal__item-name {
  min-width: 137px;
  margin-right: 40px;
  color: #262c40;
  font-size: 18px;
}
.modal__header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 40px;
}
.modal__close {
  cursor: pointer;
}
.modal__title {
  color: #262c40;
  font-size: 24px;
  font-weight: bold;
}
.modal__overlay {
  display: flex; /* Hidden by default */
  justify-content: center;
  align-items: center;
  position: fixed; /* Stay in place */
  z-index: 1; /* Sit on top */
  padding-top: 100px; /* Location of the box */
  left: 0;
  top: 0;
  width: 100%; /* Full width */
  height: 100%; /* Full height */
  overflow: auto; /* Enable scroll if needed */
  background-color: rgba(188, 195, 208, 0.5);
}
.modal__inner {
  background-color: #fefefe;
  margin: auto;
  /* padding: 20px; */
  /* border: 1px solid #888; */
  width: 500px;
  /* height: 468px; */
  border-radius: 16px;
  padding: 24px;
  padding-bottom: 56px;
}
</style>
