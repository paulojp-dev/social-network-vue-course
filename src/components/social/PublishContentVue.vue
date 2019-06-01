<template>
  <div class="row">
    <grid-vue class="input-field" size="12">
      <textarea id="publishContentID" v-model="content" class="materialize-textarea"></textarea>
      <label for="publishContentID">What's happen?</label>
    </grid-vue>
    <p>
      <grid-vue v-if="content" class="btn waves-effect waves-light col" size="2 offset-s10">Publish</grid-vue>
    </p>
  </div>
</template>

<script>
import GridVue from '@/components/layouts/GridVue'

export default {
  name: 'PublishContentVue',
  props: [],
  data () {
    return {
      content: ''
    }
  },
  components: {
    GridVue
  }
}
</script>

<style scoped>
</style>
