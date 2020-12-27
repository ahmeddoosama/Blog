<template>
  <div id="app">
    <app-header />
    <div class="container">
      <blog-card />
    </div>
  </div>
</template>

<script>

import AppHeader from './components/app-header'
import blogCard from './components/blog-card'

export default {
  name: 'app',
  components: {
    AppHeader,
    blogCard
  }
}
</script>

<style lang="scss">

</style>
