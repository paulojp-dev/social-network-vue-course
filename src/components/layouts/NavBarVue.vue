<template>
  <nav :class="color">
    <div class="nav-wrapper container">
      <router-link :to="url || '/'" class="brand-logo">{{ logo || 'Site' }}</router-link>
      <ul id="nav-mobile" class="right hide-on-med-and-down">
        <li><router-link v-if="user" to="/">Home</router-link></li>
        <li><router-link v-if="!user" to="/register">Register</router-link></li>
        <li><router-link v-if="!user" to="/login">Login</router-link></li>
        <li><router-link v-if="user" to="/profile">{{ user.name }}</router-link></li>
        <li><a v-if="user" v-on:click="logout()">Log out</a></li>
      </ul>
    </div>
  </nav>
</template>

<script>
export default {
  name: 'NavBar',
  props: ['logo', 'url', 'color'],
  data () {
    return {
    }
  },
  created () {
    this.user = null
    let userAuth = localStorage.getItem('user')

    if (userAuth) {
      this.user = JSON.parse(userAuth)
    }
  },
  methods: {
    logout () {
      localStorage.clear()
      this.user = null
      this.$router.push('/login')
    }
  }
}
</script>

<style scoped>
</style>
