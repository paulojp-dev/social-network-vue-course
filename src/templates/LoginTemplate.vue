<template>
  <div>
    <header>
      <nav-bar-vue color="blue" logo="Social" url="/">
        <li><router-link to="/">Home</router-link></li>
        <li><router-link to="/login">Login</router-link></li>
      </nav-bar-vue>
    </header>

    <main>
      <div class="container">
        <div class="row">
          <grid-vue size="8">
            <card-menu-vue>
              <slot name="left"></slot>
            </card-menu-vue>
          </grid-vue>

          <grid-vue size="4">
            <slot name="right"></slot>
          </grid-vue>
        </div>
      </div>
    </main>

    <footer-vue ano="2019" color="blue" description="Rede social" logo="Social">
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
