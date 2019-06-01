<template>
  <div>
    <header>
      <nav-bar-vue logo="Social" url="#" color="blue"></nav-bar-vue>
    </header>

    <main>
      <div class="container">
        <div class="row">
          <grid-vue size="6">
            <card-menu-vue>
            </card-menu-vue>
          </grid-vue>

          <grid-vue size="6">
            <slot></slot>
          </grid-vue>
        </div>
      </div>
    </main>

    <footer-vue color="blue" logo="Social" description="Rede social" ano="2019">
      <li><a class="grey-text text-lighten-3" href="#!">Link 1</a></li>
      <li><a class="grey-text text-lighten-3" href="#!">Link 2</a></li>
      <li><a class="grey-text text-lighten-3" href="#!">Link 3</a></li>
      <li><a class="grey-text text-lighten-3" href="#!">Link 4</a></li>
    </footer-vue>
  </div>
</template>

<script>
import NavBarVue from '@/components/layouts/NavBarVue'
import FooterVue from '@/components/layouts/FooterVue'
import GridVue from '@/components/layouts/GridVue'
import CardMenuVue from '@/components/layouts/CardMenuVue'

export default {
  name: 'LoginTemplate',
  components: {
    NavBarVue,
    FooterVue,
    GridVue,
    CardMenuVue
  }
}
</script>

<style>
</style>
