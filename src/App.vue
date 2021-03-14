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

/*
colors: 
1. datk blue #264653
2. light blue #2a9d8f
3. light yellow #e9c46a 
4. light oragne #f4a261
5. dark orange #e76f51
*/
</style>
