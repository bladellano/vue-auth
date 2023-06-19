<template>
  <h3>Home</h3>
</template>

<script>
import axios from "axios";

export default {
  name: "Home",
  async created() {
    const response = await axios.post("auth/me");
    console.log("response", response);
  },
};
</script>

<style scoped>
</style>