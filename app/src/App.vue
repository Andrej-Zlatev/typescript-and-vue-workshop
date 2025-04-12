<script lang="ts">
import TheNavbar from './components/TheNavbar.vue'
import TheFooter from './components/TheFooter.vue'
import {defineComponent} from 'vue'

const Restaurants = {
  name: 'Johns Doe Restaurant',
  address: 'Random'
}

export default defineComponent({
  name: 'App',
  components: {
    TheNavbar,
    TheFooter
  },
  data() {
    return {
      Restaurants,
    }
  }
})
</script>

<template>
  <TheNavbar :restaurants="Restaurants"/>
  <RouterView/>
  <TheFooter/>
</template>

<style></style>
