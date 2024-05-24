<script setup>
const { user } = defineProps(['user'])
</script>

<template>
  <div class="card__item">
    <div class="card__name">{{ user.name }}</div>
    <a class="card__link" :href="`tel:${user.phone}`">
      <img class="link-img" src="../assets/phone.svg" alt="" />
      <p>{{ user.phone }}</p>
    </a>
    <a class="card__link" :href="`mailto:${user.email}`">
      <img class="link-img" src="../assets/envelope.svg" alt="" />
      <p>{{ user.email }}</p>
    </a>
  </div>
</template>

<style>
.card__item {
  width: 357px;
  height: 314px;
  padding: 24px;
  border-radius: 16px;
  box-shadow: 0px 0px 20px rgba(0, 0, 0, 0.1);
  cursor: pointer;
}
.card__name {
  font-size: 24px;
  line-height: 30px;
  color: #262c40;
  font-weight: bold;
  margin-bottom: 24px;
}
.card__link {
  display: flex;
  align-items: center;
  font-size: 14px;
  color: #8189a3;
  margin-bottom: 12px;
}
.link-img {
  margin-right: 19px;
}
</style>
