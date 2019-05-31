<template>
  <card-content-vue profile="https://materializecss.com/images/yuna.jpg" name="Maria"
                    date="01/01/2019 20:35">

    <div class="card-image">
      <img alt="img" src="https://materializecss.com/images/sample-1.jpg">
      <span class="card-title">Card Title</span>
    </div>

    <div class="card-content">
      <p>I am a very simple card. I am good at containing small bits of information.
        I am convenient because I require little markup to use effectively.</p>
    </div>

  </card-content-vue>
</template>

<script>
import CardContentVue from '@/components/social/CardContentVue'
import CardDetailsVue from '@/components/social/CardDetailsVue'

export default {
  name: 'Home',
  data () {
    return {
    }
  },
  components: {
    CardContentVue,
    CardDetailsVue
  }
}
</script>

<style scoped>
</style>
