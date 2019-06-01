<template>
  <span>
    <login-template>
      <span slot="left">
        <ul>
          <img src="https://bizcapital.com.br/blog/wp-content/uploads/2019/02/Img_Redes_Sociais_para_Neg%C3%B3cios_2-2.png"
               alt="Welcome Image" class="responsive-img">
        </ul>
      </span>

      <span slot="right">
        <h2>Register</h2>

          <label for="registerNameID">Name</label>
          <input id="registerNameID" type="text" placeholder="Full name" value="" />
          <label for="registerEmailID">Email</label>
          <input id="registerEmailID" type="text" placeholder="E-mail" value="" />
          <label for="registerPasswordID">Password</label>
          <input id="registerPasswordID" type="password" placeholder="Password" value="" />
          <label for="registerConfirmPasswordID">Confirm Password</label>
          <input id="registerConfirmPasswordID" type="password" placeholder="Password confirmation" value="" />

          <button class="btn">Register</button>
          <router-link class="btn blue" to="/login">I'm already registered</router-link>
      </span>
    </login-template>
  </span>
</template>

<script>
import LoginTemplate from '@/templates/LoginTemplate'

export default {
  name: 'Register',
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
