<template>
<h1>Danh sách</h1>
<ul v-for="fruit in fruits" :key="fruit">
    <li>{{ fruit }}</li>

</ul>
<h1>{{ name }}</h1>

<button class="btn btn-primary" @click="$emit('handleEmit')">Emit</button>
<button class="btn btn-primary" @click="$emit('handleAlert')">Alert</button>

</template>

<script setup>
// props truyền qua từ component cha
defineProps({
    // object: data type
    fruits: Array,
    name: String
})
// emit
 const emit = defineEmits(['handleEmit', 'handleAlert'])
</script>