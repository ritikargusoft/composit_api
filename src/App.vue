<template>
  <section class="container">
    <h2>{{ userName }}</h2>
    <h3>{{ age }}</h3>
    <button @click="setAge">Change Age</button>

    <div class="">
      <input type="text" placeholder="First Name" v-model="setFirstName" />
      <input type="text" placeholder="Last Name" v-model="setLastName" />
    </div>
  </section>
</template>
<script>
import { ref, computed, watch } from "vue";
export default {
  setup() {
    const firstName = ref("");
    const lastName = ref("");
    const uAge = ref(31);

    const uName = computed(function () {
      return firstName.value + " " + lastName.value;
    });

    watch(uAge, function(newValue, oldValue){
console.log('Old age'+oldValue)
console.log('Old age'+newValue)
    })

    // const user = reactive({
    //   name: "Ritik",
    //   age: 20,
    // });

    function setNewAge(){
      uAge.value = 33;
    }

    // function setFirstName(event) {
    //   firstName.value = event.target.value;
    // }

    // function setLastName(event) {
    //   lastName.value = event.target.value;
    // }
    return {
      age: uAge,
      userName: uName,
      setAge: setNewAge,
      firstName:firstName,
      lastName:lastName,
    };
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


