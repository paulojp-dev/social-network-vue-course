<template>
  <span>
    <login-template>
      <h2>Login</h2>

      <label for="loginEmailID">Email</label>
      <input id="loginEmailID" type="text" placeholder="E-mail" value="" />
      <label for="loginPasswordID">Password</label>
      <input id="loginPasswordID" type="password" placeholder="Password" value="" />

      <button class="btn">Sing In</button>
    </login-template>
  </span>
</template>

<script>
import LoginTemplate from '@/templates/LoginTemplate'

export default {
  name: 'Login',
  data () {
    return {
    }
  },
  components: {
    LoginTemplate
  }
}
</script>

<style scoped>
</style>
