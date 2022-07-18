<script setup>
import { computed, ref } from 'vue';

const isOpen = ref(false);

  const users = [
    {
      id: 1,
      name: "John",
      gender: "male",
      age: 40
    },
    {
      id: 2,
      name: "Precious",
      gender: "female",
      age: 25
    },
    {
      id: 3,
      name: "David",
      gender: "male",
      age: 28
    },
    {
      id: 4,
      name: "Joshua",
      gender: "male",
      age: 28
    }
  ]

const validateUsers = computed(() => users.filter(user => user.gender == 'female'))

</script>

<template>
   <div class="container">
     <div v-for="user in users" :key="user.id"  class="card">
        <div>
          <span>{{ user.name }}</span>
          <p>age: {{ user.age }}</p>

          <p v-if="user.gender == 'male'">Your are a man</p>
          <span v-else>you are a woman</span>
        </div>
      </div>
   </div>
   <button @click="isOpen = !isOpen">show div</button>
    <div v-show="isOpen" class="box"></div>
</template>

<style scoped>
  .container{
    width: 80%;
    margin: 0px auto;
    display: flex;
    justify-content: space-between;
  }
  .card {
    display: flex;
    justify-content: center;
    align-items: center;
    width: 200px;
    height: 200px;
    border: 1px solid #eee;
  }
  .box {
    width: 400px;
    height: 200px;
    margin-top: 10px;
    background-color: black;
  }
</style>

