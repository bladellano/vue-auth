<template>
  <form @submit.prevent="handlerSubmit">
    <h3>Login</h3>

    <div class="form-group">
      <label for="">Email</label>
      <input
        type="email"
        class="form-control"
        v-model="email"
        placeholder="Email"
      />
    </div>

    <div class="form-group">
      <label for="">Password</label>
      <input
        type="password"
        class="form-control"
        v-model="password"
        placeholder="Password"
      />
    </div>

    <button class="btn btn-primary btn-block">Login</button>
  </form>
</template>

<script>

import axios from 'axios';

export default {
  name: "Login",
  data() {
    return {
      email: "a@uol.com",
      password: "123456",
    };
  },
  methods: {
    async handlerSubmit() {

      const response = await axios.post("auth/login", {
        email: this.email,
        password: this.password,
      });

      localStorage.setItem('token', response.data.access_token)

      this.$router.push('/')

    },
  },
};
</script>

<style scoped>
</style>