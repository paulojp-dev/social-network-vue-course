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
        <h2>Login</h2>

        <label for="loginEmailID">Email</label>
        <input id="loginEmailID" type="text" placeholder="E-mail" value="" />
        <label for="loginPasswordID">Password</label>
        <input id="loginPasswordID" type="password" placeholder="Password" value="" />

        <button class="btn">Sing In</button>
      </span>
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
