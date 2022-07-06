<template>
  <div class="bg-zinc-200">
    <header-component></header-component>
    <landing-component></landing-component>
    <services-component></services-component>
    <!-- <work-component></work-component> -->
    <technology-component></technology-component>
    <links-component></links-component>
    <contact-component></contact-component>
  </div>
</template>

<script>
import LandingComponent from './components/LandingComponent.vue'
import ServicesComponent from './components/ServicesComponent.vue'
import TechnologyComponent from './components/TechnologyComponent.vue'
import ContactComponent from './components/ContactComponent.vue'
import HeaderComponent from './components/HeaderComponent.vue'
import LinksComponent from './components/LinksComponent.vue'

export default {
  name: 'App',
  components: {
    LandingComponent,
    ServicesComponent,
    TechnologyComponent,
    ContactComponent,
    HeaderComponent,
    LinksComponent,
  }
}
</script>

<style>
#app {
  font-family: Montserrat, Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
}
</style>
