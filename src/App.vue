<template>
  <div class="bg-zinc-200">
    <header-component></header-component>
    <landing-component></landing-component>
    <services-component></services-component>
    <work-component></work-component>
    <technology-component></technology-component>
    <contact-component></contact-component>
    <links-component></links-component>
  </div>
</template>

<script>
import LandingComponent from './components/LandingComponent.vue'
import ServicesComponent from './components/ServicesComponent.vue'
import WorkComponent from './components/WorkComponent.vue'
import TechnologyComponent from './components/TechnologyComponent.vue'
import ContactComponent from './components/ContactComponent.vue'
import LinksComponent from './components/LinksComponent.vue'
import HeaderComponent from './components/HeaderComponent.vue'

export default {
  name: 'App',
  components: {
    LandingComponent,
    ServicesComponent,
    WorkComponent,
    TechnologyComponent,
    ContactComponent,
    LinksComponent,
    HeaderComponent,
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
