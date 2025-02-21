<template>
  <br><br>
  <h1 class="text-danger">{{count}}</h1>
  <!-- gán sự kiện @click -->
  <button @click="handlecount" class="btn btn-success">Increment</button>

  <!-- v-model -->
  <input type="text" v-model="inputText" class="form-control">
  <p>Text: {{ inputText }}</p>

  <label for="" class="form-label">Nhập ở đây: </label>
  <input type="text" v-model="inputText" class="form-control">

  <h1>{{ user.name }}</h1>
  <h1>{{ user.age }}</h1>
  <h1>{{ user.email }}</h1>

  <ul v-for="(user, index) in users" :key="user.id">
    <li>{{ index + 1 }} - {{ user.name }}</li>
    <li>{{ user.age }}</li>
    <li>{{ user.email }}</li>
  </ul>

<!-- day3 -->
 <!-- Cộng chuỗi -->
 <h1> {{ firstName }} - {{ lastName }}</h1>
 <h3>{{ fullName }}</h3>
 <!-- if-else -->
  <input type="text" v-model="age" class="form-control">
  <p v-if="!canResiter">Đủ điều kiện</p>
  <p v-else>Không đủ điều kiện</p>

  <h1>Danh sách người dùng</h1>
  <ul v-for="user in users" :key="user.id">
    <li >
      {{ user.name }} - {{ user.age }}
    </li>
  </ul>
  <h1> lớn hơn 18 </h1>
  <ul v-for="user in adultUsers" :key="user.id">
      <li>
        {{ user.name }} - {{ user.age }}
      </li>
  </ul>



</template>








<script setup>

// import thư viện
import { computed, reactive, ref } from "vue";

// khởi tạo giá trị ban đầu ~ number or text
// ref thường dùng cho number, text
const count = ref("0");
const inputText = ref('');



// reactive - muốn dùng thì user.name, user.age, user.email không cần .value, thường dùng cho object, json
const user = reactive({
  name: 'tuan', age: 20, email: "trantuan88261@gmail.com"
})


//v-for ~ vòng lặp
const users = reactive([
  {name: 'tuan', age: 11, email: "trantuan88261@gmail.com"},
  {name: 'hoang', age: 30, email: "hoang@gmail.com"},
  {name: 'nam', age: 25, email: "nam@gmail.com"}
])
// function thường của js
// arrow function
// @click
const handlecount = () => {
count.value++;
}

// day3
const firstName = ref('Trần');
const lastName = ref('Tuấn');
// cộng chuỗi
const fullName = computed(() => 
  `${firstName.value} ${lastName.value}`
  )
// if-else
const age = ref(0);
const canResiter  = computed(() => age.value >=18)

// computed là việc với mảng
const adultUsers = computed(() => users.filter(user => user.age >= 18))

// props truyền dữ liệu từ component cha xuống component con
</script> 