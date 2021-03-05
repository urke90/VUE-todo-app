<template>
    <the-header title="VUE ToDo"></the-header>
</template>

<script>
import TheHeader from './components/header/TheHeader.vue';

export default {
    name: 'App',
    components: {
        TheHeader
    }
};
</script>

<style>
* {
    margin: 0;
    padding: 0;
}
#app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
}
</style>
