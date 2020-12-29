<template>
  <main>
    <app-header>
      <h1 class="header__title">
        Blog
      </h1>
    </app-header>
    <div class="container" v-if="blogs">
      <blog-card v-for="blog in blogs" :key="blog.id" :data="blog"></blog-card>

      <button
        type="button"
        class="load-more-btn"
        @click="loadMore"
        v-if="blogs && blogs.length < totalCount"
      >
        Load More
      </button>
    </div>
  </main>
</template>

<script>
import AppHeader from "../components/app-header";
import blogCard from "../components/blog-card";
import axios from "axios";

export default {
  name: "home",
  data() {
    return {
      blogs: null,
      totalCount: null,
      page: 1
    };
  },
  components: {
    AppHeader,
    blogCard
  },
  mounted() {
    this.getBlogs(this.page);
  },
  methods: {
    getBlogs(page) {
      axios
        .get(`http://localhost:3000/blog?_page=${page}&_limit=6`)
        .then(response => {
          /* check the blog is empty or not,
         if empty add new response.data
         else concat new response.data with current data*/
          this.blogs = this.blogs
            ? this.blogs.concat(response.data)
            : response.data;

          // Get count data from json file header
          this.totalCount = response.headers["x-total-count"];
          console.log(this.totalCount);
        });
    },
    loadMore() {
      this.page++;
      this.getBlogs(this.page);
    }
  }
};
</script>

<style lang="scss">
/* imports blog-cards Variables and colors */
@import "../assets/scss/global/colors";
@import "../assets/scss/global/variables";

main {
  .container {
    display: flex;
    flex-wrap: wrap;
    .load-more-btn {
      color: $white;
      background-color: $mainColor;
      border: none;
      padding: 10px 25px;
      font-size: 18px;
      line-height: 1;
      margin: 50px auto;
    }
    @media #{$smallDevices} {
      display: block;
    }
  }
}
</style>
