<template>
    <div id="app">
        <router-view />
        <Footer />
    </div>
</template>

<script>
import Footer from './components/Footer.vue';

export default {
    name: 'App',
    components: {
        Footer,
    },
};
</script>

<style lang="scss">
@import './assets/scss/styles.scss';
</style>
