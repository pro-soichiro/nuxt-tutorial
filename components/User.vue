<template>
  <tr>
    <td>{{ user.id }}</td>
    <td>{{ user.name }}</td>
    <td>{{ user.age }}</td>
  </tr>
</template>

<script>
export default {
  props: ["user"],
};
</script>
