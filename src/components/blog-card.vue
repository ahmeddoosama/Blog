<template>
<div class="card">
    <div class="card__img">
        <div class="ratio-content">
            <img :src="data.image" alt="image">
        </div>
    </div>

    <div class="card__content">
        <h2 class="card__title">
            {{ data.title }}
        </h2>
        <p class="card__summry">
            {{ data.summry }}
        </p>

        <router-link :to="`/blog/${data.id}`" class="card__btn">
            Continue reading
        </router-link>
    </div>
</div>
</template>

<script>
export default {
    name: 'card',
    props: {
        data: {
            required: true
        }
    }
}
</script>

<style lang="scss" scoped>

/* imports blog-cards Variables and colors */
@import '../assets/scss/global/colors';
@import '../assets/scss/global/variables';

.card {
    width: 33%;
    padding: 30px 10px 0;
    .card__img {
        position: relative;
        margin-bottom: 15px;
        &::before {
            content: '';
            display: block;
            padding-top: 66.5%;
        }
        img {
            border-radius: 5px;
        }
    }
    .card__content {
        color: $gray;
        .card__title {
            color: $mainColor;
            font-size: 20px;
            font-weight: $font-weight-700;
            margin-bottom: 7px;
        }
        .card__summry {
            font-weight: $font-weight-400;
            color: $smokeGray;
            font-size: 16px;
            margin: 10px 0;
        }
        .card__btn {
            font-size: 14px;
            font-weight: $font-weight-400;
            font-style: italic;
        }
    }
}
</style>