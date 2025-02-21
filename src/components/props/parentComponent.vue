<template>
    <ChildComponent :fruits="fruits"
    :name="name" 
    @handleEmit="HeheEmit" @handleAlert="HeheAlert"/>
</template>

<script setup>
import{ ref } from 'vue';
import ChildComponent from './childComponent.vue';
// props truyền dữ liệu từ component cha xuống component con

const fruits = ref(['Apple', 'Banana', 'Orange']);
const name = ref('Tuấn');

// emit dùng cho click - focus - onChange
// thằng nào nhận vo props thì không call api
const HeheEmit = () => {
    alert('biết cái cc');
}

const HeheAlert = () => {
    alert('cccccccccccccc');
}
</script>