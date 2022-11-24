<template>
  <div>
    <h3>home</h3>
    <NuxtLink to="/">go to top</NuxtLink>
    <ApplyForm
      :props="{ from: 'fromHome', to: '/', newUser: newUser, method: pushUser }"
    />
    <pre>{{ users }}</pre>
  </div>
</template>

<script>
export default {
  data() {
    return {
      newUser: {
        name: "",
        age: null,
      },
      users: []
    };
  },
  methods: {
    pushUser() {
      if( this.newUser.name === '' || this.newUser.age === null ) return
      const newVal = {...this.newUser}
      this.users.push(newVal)
      this.newUser.name = ''
      this.newUser.age = null
    },
  },
};
</script>
