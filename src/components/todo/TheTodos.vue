<template>
    <div class="todos__wrapper">
        <todos-nav></todos-nav>
        <main>
            <h2>CONTENT</h2>
        </main>
    </div>
</template>

<script>
import TodosNav from './navigation/TodosNav';

export default {
    components: {
        TodosNav
    }
};
</script>

<style scoped>
.todos__wrapper {
    max-width: 700px;
    margin: 50px auto;
    padding: 0 15px;
}
</style>
