<template>
  <div class="row">
    <div class="card">
      <div class="card-content">

        <div class="row valign-wrapper">
          <grid-vue size="1">
            <img :src="profile" :alt="name" class="circle responsive-img">
            <!-- notice the "circle" class -->
          </grid-vue>

          <grid-vue size="11">
                  <span class="black-text">
                  <strong>{{ name }}</strong> - <small>{{ date }}</small>
                </span>
          </grid-vue>
        </div>

        <slot></slot>

        <div class="card-action">
          <p>
            <i class="material-icons">favorite_border</i>
            <i class="material-icons">insert_comment</i>
          </p>
        </div>

      </div>
      <div class="card-action">
        <a href="#">This is a link</a>
        <a href="#">This is a link</a>
      </div>
    </div>
  </div>
</template>

<script>
import GridVue from '@/components/layouts/GridVue'

export default {
  name: 'CardContentVue',
  props: ['profile', 'name', 'date'],
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
