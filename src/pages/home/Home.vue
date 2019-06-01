<template>
  <site-template>
    <span slot="left-menu">
      <div class="row valign-wrapper">
        <grid-vue size="4">
          <img alt="" class="circle responsive-img" src="https://materializecss.com/images/yuna.jpg">
        </grid-vue>

        <grid-vue size="8">
          <span class="black-text">
            <h5>Amanda</h5>
            desc.
          </span>
        </grid-vue>
      </div>
    </span>

    <span slot="content">
      <publish-content-vue></publish-content-vue>

      <card-content-vue
        date="01/01/2019 20:35"
        name="Maria"
        profile="https://materializecss.com/images/yuna.jpg">

        <card-details-vue
          img="https://materializecss.com/images/sample-1.jpg"
          text="I am a very simple card. I am good at containing small bits of information.
                I am convenient because I require little markup to use effectively."
          title="Card Title">
        </card-details-vue>
      </card-content-vue>
    </span>
  </site-template>
</template>

<script>
import SiteTemplate from '@/templates/SiteTemplate'
import CardContentVue from '@/components/social/CardContentVue'
import CardDetailsVue from '@/components/social/CardDetailsVue'
import PublishContentVue from '@/components/social/PublishContentVue'
import GridVue from '@/components/layouts/GridVue'

export default {
  name: 'Home',
  data () {
    return {
    }
  },
  components: {
    SiteTemplate,
    CardContentVue,
    CardDetailsVue,
    PublishContentVue,
    GridVue
  }
}
</script>

<style scoped>
</style>
