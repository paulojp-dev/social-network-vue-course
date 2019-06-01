<template>
  <span>
    <publish-content-vue></publish-content-vue>

    <card-content-vue
      profile="https://materializecss.com/images/yuna.jpg"
      name="Maria"
      date="01/01/2019 20:35">

      <card-details-vue
        img="https://materializecss.com/images/sample-1.jpg"
        title="Card Title"
        text="I am a very simple card. I am good at containing small bits of information.
              I am convenient because I require little markup to use effectively.">
      </card-details-vue>
    </card-content-vue>
  </span>
</template>

<script>
import CardContentVue from '@/components/social/CardContentVue'
import CardDetailsVue from '@/components/social/CardDetailsVue'
import PublishContentVue from '@/components/social/PublishContentVue'

export default {
  name: 'Home',
  data () {
    return {
    }
  },
  components: {
    CardContentVue,
    CardDetailsVue,
    PublishContentVue
  }
}
</script>

<style scoped>
</style>
