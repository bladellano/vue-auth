<template>
  <form @submit.prevent="handlerSubmit">
    <h3>Sign Up</h3>

    <div class="form-group">
      <label for="">First Name</label>
      <input
        type="text"
        class="form-control"
        v-model="name"
        placeholder="First Name"
      />
    </div>

    <div class="form-group">
      <label for="">Last Name</label>
      <input
        type="text"
        class="form-control"
        v-model="last_name"
        placeholder="Last Name"
      />
    </div>

    <div class="form-group">
      <label for="">E-mail</label>
      <input
        type="email"
        class="form-control"
        v-model="email"
        placeholder="E-mail"
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

    <div class="form-group">
      <label for="">Confirm Password</label>
      <input
        type="password"
        class="form-control"
        v-model="password_confirm"
        placeholder="Confirm Password"
      />
    </div>

    <button class="btn btn-primary btn-block">Sign Up</button>
  </form>
</template>

<script>

import axios from "axios";

export default {
  name: "Register",
  data() {
    return {
      name: "a",
      last_name: "a",
      email: "a@uol.com",
      password: "123456",
      password_confirm: "123456",
    };
  },
  methods: {
    async handlerSubmit() {

       await axios.post("users", {
        name: this.name,
        last_name: this.last_name,
        email: this.email,
        password: this.password,
        password_confirm: this.password_confirm,
      }).catch((error)=>{
         alert(error.response.data.message)
      });

      this.$router.push('/login')
    },
  },
};
</script>

<style scoped>
</style>