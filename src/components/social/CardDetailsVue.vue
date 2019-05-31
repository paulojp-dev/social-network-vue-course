<template>
  <span>
    <div v-if="img" class="card-image">
      <img :alt="alt || ''" :src="img">
      <span class="card-title">{{ title || ''}}</span>
    </div>

    <div v-if="text" class="card-content">
      <p>{{ text }}</p>
    </div>
  </span>
</template>

<script>
import GridVue from '@/components/layouts/GridVue'

export default {
  name: 'CardDetailsVue',
  props: ['img', 'alt', 'title', 'text'],
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
