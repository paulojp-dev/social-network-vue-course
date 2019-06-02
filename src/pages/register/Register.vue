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
          <input id="registerNameID" placeholder="Full name" type="text" v-model="user.name" />
           <label for="registerEmailID">Email</label>
          <input id="registerEmailID" type="text" placeholder="E-mail" v-model="user.email" />
          <label for="registerPasswordID">Password</label>
          <input id="registerPasswordID" placeholder="Password" type="password" v-model="user.password" />
          <label for="registerConfirmPasswordID">Confirm Password</label>
          <input id="registerConfirmPasswordID" placeholder="Password confirmation" type="password"
                 v-model="user.password_confirmation" />

          <button class="btn" v-on:click="register()">Register</button>
          <router-link class="btn blue" to="/login">I'm already registered</router-link>
      </span>
    </login-template>
  </span>
</template>

<script>
import LoginTemplate from '@/templates/LoginTemplate'
import axios from 'axios'

export default {
  name: 'Register',
  data () {
    return {
      'user': {
        'name': '',
        'email': '',
        'password': '',
        'password_confirmation': ''
      }
    }
  },
  components: {
    LoginTemplate
  },
  methods: {
    register () {
      axios.post('http://127.0.0.1:8000/api/register', {
        name: this.user.name,
        email: this.user.email,
        password: this.user.password,
        password_confirmation: this.user.password_confirmation
      }, {
        headers: {
          'Content-Type': 'application/json',
          'Cache-Control': 'no-cache'
        }
      }).then(response => {
        if (response.status >= 200 && response.data.token) {
          this.$router.push('/login')
        } else {
          console.log('statusCode ' + response.status + ' not expected')
        }
      }).catch(e => {
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
