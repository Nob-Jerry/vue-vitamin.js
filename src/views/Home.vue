<template>
  <h1 class="text-danger">{{count}}</h1>
  <button @click="handlecount" class="btn btn-success" >Increment</button>

  <p>Text: {{ inputText }}</p>

  <label for="" class="form-label">Nhập ở đây: </label>
  <input type="text" v-model="inputText" class="form-control">

  <h1>{{ user.name }}</h1>
  <h1>{{ user.age }}</h1>
  <h1>{{ user.email }}</h1>


  <ul v-for="(user, index) in users" key="user.id">
    <li>{{ index + 1 }} - {{ user.name }}</li>
    <li>{{ user.age }}</li>
    <li>{{ user.email }}</li>
  </ul>

  <table class="table"></table>

</template>

<script setup>



import { reactive,ref } from "vue";
// khi muốn sử dụng biến khai báo với ref thì phải .value

// khởi tạo giá trị ban đầu ~ number or text
const count = ref(0);

const inputText = ref('')

// reactive - muốn dùng thì user.name, user.age, user.email
// được sử dụng để tạo đối tượng hoặc mảng phản ứng 
// tất cả thuộc tính bên tỏng reactive đều là đói tượng phản ứng
const user = reactive({
  name: 'tuan', age: 20, email: "trantuan88261@gmail.com"
})

//v-for ~ vòng lặp
const users = reactive(
  {name: 'tuan', age: 25, email: "trantuan88261@gmail.com"},
  {name: 'hoang', age: 23, email: "hoang@gmail.com"},
  {name: 'nam', age: 25, email: "nam@gmail.com"},
  {name: 'minh', age: 25, email: "minh@gmail.com"},
  {name: 'hung', age: 27, email: "hung@gmail.com"},
)

// arrow function
// @click
const handlecount = () => {
count.value++;
}
</script>