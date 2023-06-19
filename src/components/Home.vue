<template>
  <div>
    <h3 v-if="user">Hi, {{ user.name }} </h3>
    <h3 v-if="!user">You are not logged in!</h3>
  </div>
</template>

<script>

export default {
  name: "Home",
  props: ['user'],
};
</script>

<style scoped>
</style>