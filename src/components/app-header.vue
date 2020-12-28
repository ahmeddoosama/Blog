<template>
    <header>
        <slot></slot>
    </header>
</template>

<script>
export default {
    name: 'appHedaer'
}
</script>

<style lang="scss" scoped>

// imports Header Variables and colors
@import '../assets/scss/global/colors';
@import '../assets/scss/global/variables';

header {
    position: relative;
    height: 250px;
    display: flex;
    justify-content: center;
    align-items: center;
    background-image: url('../assets/images/background/header-bg.a681f959.jpg');
    background-size: cover;
    &::before {
        content: '';
        display: block;
        position: absolute;
        top: 0;
        bottom: 0;
        left: 0;
        right: 0;
        opacity: 0.95;
        background-image: $bgHeader-linearGrediant;
    }
    .header__title {
        position: relative;
        color: $white;
        font-weight: $font-weight-300;
        font-size: 60px;
    }
    .back-btn {
        color: $white;
        position: absolute;
        top: 20px;
        left: 20px;
        background-color: rgba(255, 255, 255, 0.1);
        border-radius: 5px;
        padding: 7px 15px;
        line-height: 1;
        &:hover {
            background-color: rgba(255, 255, 255, 0.3);
        }
    }
}
</style>