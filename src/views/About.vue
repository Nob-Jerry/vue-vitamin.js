<template>
  <h1>Thông tin cá nhân</h1>
  <label for="" class="form-label">Họ và tên: </label>
  <input type="text" v-model="user.name" class="form-control">
  <label for="" class="form-label">Tuổi: </label>
  <input type="number" v-model="user.age" class="form-control">
  <label for="" class="form-label">Email: </label>
  <input type="text" v-model="user.mail" class="form-control">

  <h1>kết quả</h1>
  <div class="card">
    <div class="card-body">
      <p> Họ và tên: {{ user.name }}</p>
      <p> Tuổi: {{ user.age }}</p>
      <p> Email: {{ user.mail }}</p>
    </div>
  </div>
</template>
<script setup>
//computed tìm hiểu trước khi sử dụng
//example: mã năm học: 2021-2022 => NH2122
// tìm hiểu thêm emit và props
import { reactive } from "vue";
const user = reactive({
  name: '',
   age: '', 
   mail: ''})
</script>