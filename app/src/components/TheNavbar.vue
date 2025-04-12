<script lang="ts">

import type {PropType} from "vue";
import {defineComponent} from "vue";

type Restaurants = {
  name: string,
  address: string,
}

export default defineComponent({
  props: {
    tagline: {
      type: String,
    },
    restaurants: Object as PropType<Restaurants>
  },


  data: () => ({
    navList: [
      {
        name: 'Home',
        path: '/',
      },
      {
        name: 'Restaurants',
        path: '/restaurants',
      },
      {
        name: 'Dishes',
        path: '/dishes',
      },
    ],
  }),
})
</script>

<template>
  <nav class="navbar has-shadow">
    <div><p>
      {{ restaurants.name }} {{ restaurants.address }}
    </p>
    </div>
    <div class="navbar-brand">
      <RouterLink to="/" class="navbar-item">
        <img src="@/assets/to-eat-logo.svg" alt="" width="100"/>
      </RouterLink>
    </div>
    <div class="navbar-menu">
      <div class="navbar-start">
        <div class="navbar-item">
          <small>{{ tagline }}</small>
        </div>
      </div>
      <div class="navbar-end">
        <div v-for="navItem in navList" class="navbar-item" :key="`nav-${navItem.name}`">
          <RouterLink :to="navItem.path">{{ navItem.name }}</RouterLink>
        </div>
      </div>
    </div>
  </nav>
</template>

<style></style>
