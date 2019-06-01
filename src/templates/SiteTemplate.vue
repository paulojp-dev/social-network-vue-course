<template>
  <div>
    <header>
      <nav-bar-vue logo="Social" url="#/" color="blue">
        <li><a href="#/">Home</a></li>
        <li><a href="#/login">Login</a></li>
      </nav-bar-vue>
    </header>

    <main>
      <div class="container">
        <div class="row">
          <grid-vue size="3">
            <card-menu-vue>
              <slot name="left-menu"></slot>
            </card-menu-vue>
          </grid-vue>

          <grid-vue size="9">
            <slot name="content"></slot>
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
  name: 'SiteTemplate',
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
