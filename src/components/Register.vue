<template>
  <form class="register" @submit.prevent="register">
    <h1>Register</h1>
    <label for="username">Username:</label>
    <input type="text" name="username" v-model="username">
    <label for="full_name">Full Name:</label>
    <input type="text" name="full_name" v-model="full_name">
    <label for="email">Email:</label>
    <input type="email" name="email" v-model="email">
    <label for="password">Password:</label>
    <input type="password" name="password" v-model="password">
    <hr />
    <button type="submit"> Submit</button>
  </form>
</template>

<script>
export default {
  name: "Register",
  data() {
    return {
      username: "",
      full_name: "",
      email: "",
      password: "",
    };
  },
  methods: {
    login() {
      const userData = {
        username: this.username,
        full_name: this.full_name,
        email: this.email,
        password: this.password,
      };
      this.$store.dispatch('AUTH_REQUEST', userData).then(() => this.$router.push("/"));
    },
  },
}
</script>

<style scoped>
.register {
  display: flex;
  flex-direction: column;
  width: 300px;
  padding: 10px;
  margin: 0 auto;
}

.register  input, button {
  border: 1px solid black;
  border-radius: 5px;
}

hr {
  margin: 10px 0;
}
</style>