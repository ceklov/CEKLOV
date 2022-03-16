<template>
  <div class="bg-zinc-200">
    <header-component></header-component>
    <picture-component></picture-component>
    <services-component></services-component>
    <work-component></work-component>
    <contact-component></contact-component>
    <links-component></links-component>
  </div>
</template>

<script>
import PictureComponent from './components/PictureComponent.vue'
import ServicesComponent from './components/ServicesComponent.vue'
import WorkComponent from './components/WorkComponent.vue'
import ContactComponent from './components/ContactComponent.vue'
import LinksComponent from './components/LinksComponent.vue'
import HeaderComponent from './components/HeaderComponent.vue'

export default {
  name: 'App',
  components: {
    PictureComponent,
    ServicesComponent,
    WorkComponent,
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
