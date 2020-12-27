<template>
<div class="card">
    <div class="card__img">
        <img src="" alt="">
    </div>

    <div class="card__content">
        <h2 class="card__title"></h2>
        <p class="card__summry"></p>
        <a class="card__btn" href=""></a>
    </div>
</div>
</template>

<script>
export default {
    name: 'card'
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
        img {
            width: 100%;
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
            margin-top: 0;
            font-weight: $font-weight-300;
        }
        .card__btn {
            font-size: 14px;
            font-weight: $font-weight-400;
            font-style: italic;
        }
    }
}
</style>