<template>
  <div>
    <h3>index</h3>
    <NuxtLink to="/home">go to home</NuxtLink>
    <!-- <a href="https://nuxtjs.org">go to nuxt</a> -->
    <!-- <button @click="show = !show">Show list</button>
    <LazyMountainsList v-if="show" /> -->

    <pre>{{ newUser }}</pre>
    <pre>{{ typeof newUser.age }}</pre>
    <ApplyForm :props="{ from: 'fromIndex', to: '/home', newUser: newUser, method: pushUser }" />

    <p>form component</p>
    <table>
      <thead>
        <tr>
          <th>id</th>
          <th>name</th>
          <th>age</th>
        </tr>
      </thead>
      <tbody>
        <User v-for="(user, index) in users" :user="user" :key="index" />
      </tbody>
    </table>
  </div>
</template>

<script>
export default {
  name: "IndexPage",
  data() {
    return {
      show: false,
      newUser: {
        name: "",
        age: null,
      },
      users: [
        {
          id: 1,
          name: "bob",
          age: 24,
        },
        {
          id: 2,
          name: "sum",
          age: 32,
        },
      ],
    };
  },
  methods: {
    pushUser() {
      if( this.newUser.name === '' || this.newUser.age === null ) return
      const newVal = {...this.newUser}
      this.users.push(newVal)
      this.newUser.name = ''
      this.newUser.age = null
    }
  }
};
</script>
