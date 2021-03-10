<template>
    <the-header title="VUE ToDo"></the-header>
    <the-todos></the-todos>
</template>

<script>
import TheHeader from './components/header/TheHeader.vue';
import TheTodos from './components/todo/TheTodos.vue';

export default {
    name: 'App',
    components: {
        TheHeader,
        TheTodos
    }
};
</script>

<style>
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}
body {
    background-color: #264653;
}
ul {
    list-style-type: none;
}
</style>
