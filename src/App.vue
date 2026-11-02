<template>

<ul>
  <li v-for="(tasks, index) in tasks" :key="index">
    {{ tasks.name }}: {{ tasks.completed ? '(done)' : '(to do)' }}
    <button @click="toggleCompletion(index)">Toggle</button>
  </li>
  
</ul>




</template>

<script setup>
import { ref } from 'vue';

const tasks = ref([
  {name: 'doing groceries', completed: false},
  {name: 'washing dishes', completed: true},
  {name: 'walking the dog', completed: false}
]);

const toggleCompletion = (x) => {
 tasks.value[x].completed = !tasks.value[x].completed;
}

// function toggleCompletion(x) {
//   if (tasks[x].completed == true) {
//     tasks[x].completed = false;
//   } else {
//     tasks[x].completed = true;
//   };
// }

</script>
