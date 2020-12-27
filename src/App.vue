<template>
  <div id="app">
    <app-header />
    <div class="container" v-if="blogs">
      <blog-card
        v-for="blog in blogs"
        :key="blog.id"
        :data="blog"></blog-card>
    </div>
  </div>
</template>

<script>

import AppHeader from './components/app-header';
import blogCard from './components/blog-card';
import axios from 'axios';


export default {
  name: 'app',
  data() {
    return {
      blogs: null
    }
  },
  components: {
    AppHeader,
    blogCard
  },
  mounted() {
    axios.get('http://localhost:3000/blog').then((response) => {
      this.blogs = response.data;
    })
  }
}
</script>

<style lang="scss">

</style>
