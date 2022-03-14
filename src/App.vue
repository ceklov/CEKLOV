<template>
  <picture-component></picture-component>
  <services-component></services-component>
  <work-component></work-component>
  <contact-component></contact-component>
</template>

<script>
import PictureComponent from './components/PictureComponent.vue'
import ServicesComponent from './components/ServicesComponent.vue'
import WorkComponent from './components/WorkComponent.vue'
import ContactComponent from './components/ContactComponent.vue'

export default {
  name: 'App',
  components: {
    PictureComponent,
    ServicesComponent,
    WorkComponent,
    ContactComponent,
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
