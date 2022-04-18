<template>
  <section class="container">
    <!-- <h2>{{ userName }}</h2>
    <h3>{{ age }}</h3> -->

    <h2>{{ user.name }}</h2>
    <h3>{{ user.age }}</h3>

    <!-- <button @click="setNewAge">Change Age</button> -->
    <!-- <button @click="user.age = 30">Change Age</button> -->
    <button @click="setAge">Change Age</button>
  </section>
</template>

<script>
// import { ref } from 'vue';

import { reactive } from 'vue';

// import { reactive, toRefs } from 'vue';

export default {
  // data() {
  //   return {
  //     userName: 'Mayuri',
  //     age: 31,
  //   };
  // },
  // methods: {
  //   setNewAge() {
  //     this.age = 30;
  //   },
  // },
  setup() {
    // const uName = 'Mayuri';

    // const uName = ref('Mayuri');
    // const uAge = ref(32);

    // const user = ref({
    //   name: 'Mayuri',
    //   age: 32,
    // });

    const user = reactive({
      name: 'Mayuri',
      age: 32,
    });
    // setTimeout(function () {
    //   // uName = 'Mayu';

    //   // uName.value = 'Mayu';
    //   // uAge.value = 30;

    //   // user.value.name = 'Mayu';
    //   // user.value.age = 30;

    //   user.name = 'Mayu';
    //   user.age = 30;
    // }, 2000);

    function setNewAge() {
      user.age = 30;
    }

    // const userRefs = toRefs(user);
    // return { userName: uName, age: uAge };

    // return { userName: user.value.name, age: user.value.age };

    return { user: user, setAge: setNewAge };

    // return { userName: userRefs.name, age: userRefs.age };
  },
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
