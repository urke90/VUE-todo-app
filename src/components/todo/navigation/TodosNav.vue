<template>
    <nav class="todos__nav">
        <mobile-nav></mobile-nav>
        <desktop-nav></desktop-nav>
    </nav>
</template>

<script>
import MobileNav from './MobileNav.vue';
import DesktopNav from './DesktopNav.vue';

export default {
    components: {
        MobileNav,
        DesktopNav
    }
};
</script>

<style scoped>
.todos__nav {
    background-color: #2a9d8f;
    display: flex;
    position: relative;
    padding: 15px;
    margin-bottom: 50px;
    min-height: 60px;
}
</style>
