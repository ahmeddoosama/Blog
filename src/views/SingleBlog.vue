<template>
    <div class="blog" v-if="blog">
        <app-header>
            <router-link to="/" type="button" class="back-btn">Back</router-link>
            <h1 class="header__title">
                {{ blog.title }}
            </h1>
        </app-header>
        <div class="blog__content">
            <div class="container">
                <div class="blog__img">
                    <div class="ratio-content">
                        <img :src="blog.image" alt="images" />
                    </div>
                </div>

                <h2 class="blog__title">{{ blog.title }}</h2>
                <p class="blog__text">{{ blog.content }}</p>
            </div>
        </div>
    </div>
</template>

<script>

import axios from 'axios';
import AppHeader from "../components/app-header";

export default {
    name: "singleBlog",
    data() {
        return {
            blog: null
        }
    },
    components: {
        AppHeader
    },
    mounted() {
        axios.get('http://localhost:3000/blog/' + this.$route.params.id).then(response => {
            this.blog = response.data
        })
    }
}
</script>

<style lang="scss" scoped>

/* imports SingleBlog Variables and colors */
@import "../assets/scss/global/colors";
@import "../assets/scss/global/variables";

.blog__content {
    .blog__img {
        position: relative;
        &::before {
            content: '';
            display: block;
            padding-top: 30%;
        }
    }
    .blog__title {
        color: $mainColor;
    }
    .blog__text {
        color: $gray;
        font-style: italic;
    }
}
</style>