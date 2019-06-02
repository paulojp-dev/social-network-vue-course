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
          'Content-Type': 'application/json',
          'Cache-Control': 'no-cache'
        }
      }).then(response => {
        if (response.status >= 200 && response.data.token) {
          console.log('successfully logged in!')
          localStorage.setItem('auth', JSON.stringify(response.data))
        } else if (response.status === 403) {
          console.log('invalid credentials!')
        } else {
          console.log('statusCode ' + response.status + ' not expected')
        }
      }).catch(e => {
        console.log('99')
        switch (e.response.status) {
          case 423:
            let errors = ''

            for (let error of Object.values(e.response.data)) {
              errors += error + ' '
            }

            alert(errors)
            break
          case 403:
            console.log('invalid credentials!')
            break
          case 500:
            console.log('API internal error')
            break
          default:
            console.log('statusCode ' + e.response.status + ' not expected')
        }
      })
    }
  }
}
</script>

<style scoped>
</style>
