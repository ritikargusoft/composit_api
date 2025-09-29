<template>
  <section class="container">
    <h2>{{ user.age }}</h2>
    <h3>{{ user.name }}</h3>
    <button @click="setAge">Change Age</button>
  </section>
</template>

<script>
// import { ref } from 'vue';
import { reactive } from 'vue';
// import func from 'vue-editor-bridge';

export default {
  setup() {
    // const uName = ref('Maximilian');
    // const uAge = ref(31);
    const user = reactive({
      name: 'Ritik',
      age: 20,
    });

    setTimeout(function () {
      user.name = 'Ritik';
      user.age = 22;
    });

    return { user: user };
  },
  // data() {
  //   return {
  //     userName: 'Maximilian',
  //     age: 31
  //   };
  // },
  // methods: {
  //   setNewAge() {
  //     this.age = 32;
  //   }
  // }
};
</script>

<style>
* {
  box-sizing: border-box;
}

html {
  font-family: sans-serif;
}

body {
  margin: 0;
}

.container {
  margin: 3rem auto;
  max-width: 30rem;
  border-radius: 12px;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.26);
  padding: 1rem;
  text-align: center;
}
</style>
