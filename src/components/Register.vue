<template>
  <div>
    <h1>Register</h1>

    <input
      v-model="email"
      type="email"
      name="email"
      placeholder="email"
    >

    <input
      v-model="password"
      type="password"
      name="password"
      placeholder="password"
    >

    <button
      type="submit"
      @click="register"
    >
      Register
    </button>
  </div>
</template>

<script>
import AuthenticationService from '@/services/AuthenticationService';

export default {
  data() {
    return {
      email: '',
      password: '',
    };
  },
  watch: {
    email(value) {
      console.log(`valor do email foi alterado para: ${value}`);
    },
  },
  methods: {
    async register() {
      await AuthenticationService.register({
        email: this.email,
        password: this.password,
      });
    },
  },
};
</script>

<style scoped>
</style>
