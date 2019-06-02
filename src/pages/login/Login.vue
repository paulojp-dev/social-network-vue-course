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
          <input id="loginEmailID" type="text" placeholder="E-mail" v-model="user.email" />
          <label for="loginPasswordID">Password</label>
          <input id="loginPasswordID" type="password" placeholder="Password" v-model="user.password" />

          <button class="btn" v-on:click="login">Sing In</button>
          <router-link class="btn orange" to="/register">Register</router-link>
      </span>
    </login-template>
  </span>
</template>

<script>
import LoginTemplate from '@/templates/LoginTemplate'
import axios from 'axios'

export default {
  name: 'Login',
  data () {
    return {
      user: {
        'email': '',
        'password': ''
      }
    }
  },
  components: {
    LoginTemplate
  },
  methods: {
    login () {
      axios.post('http://127.0.0.1:8000/api/login', {
        email: this.user.email,
        password: this.user.password
      }, {
        headers: {
          'Content-Type': 'application/json'
        }
      }).then(response => {
        if (response.status === 200) {
          console.log('successfully logged in!')
        } else {
          console.log('StatusCode ' + response.status + ' not expected')
        }
      }).catch(e => {
        switch (e.response.status) {
          case 423:
            console.log('Validation error')
            break
          case 500:
            console.log('API internal error')
            break
          default:
            console.log('StatusCode ' + e.response.status + ' not expected')
        }
      })
    }
  }
}
</script>

<style scoped>
</style>
