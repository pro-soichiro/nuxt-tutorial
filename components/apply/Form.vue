<template>
  <form @submit.prevent >
    <hr />
    <label>
      name
      <input type="text" v-model="props.newUser.name" />
    </label>
    <br />
    <label>
      age
      <input type="number" v-model.number="props.newUser.age" />
    </label>
    <br />
    <button @click="props.method" >submit</button>
    <hr />

    <NuxtLink :to="props.to">go to {{ props.from }}</NuxtLink>
  </form>
</template>

<script>
export default {
  props: ["props"],
};
</script>
