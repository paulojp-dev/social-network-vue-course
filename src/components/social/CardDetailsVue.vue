<template>
  <span>
    <div class="card-image">
      <img alt="img" src="https://materializecss.com/images/sample-1.jpg">
      <span class="card-title">Card Title</span>
    </div>

    <div class="card-content">
      <p>I am a very simple card. I am good at containing small bits of information.
        I am convenient because I require little markup to use effectively.</p>
    </div>
  </span>
</template>

<script>
import GridVue from '@/components/layouts/GridVue'

export default {
  name: 'CardDetailsVue',
  props: [],
  data () {
    return {
    }
  },
  components: {
    GridVue
  }
}
</script>

<style scoped>
</style>
