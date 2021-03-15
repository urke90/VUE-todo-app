<template>
    <ul class="todo__list">
        <todo-item
            v-for="todo in storedTodos"
            :key="todo.id"
            :title="todo.title"
            :id="todo.id"
            :completed="todo.completed"
            :description="todo.description"
        ></todo-item>
    </ul>
</template>

<script>
import TodoItem from './TodoItem.vue';

export default {
    components: {
        TodoItem
    },
    inject: ['storedTodos']
};
</script>

<style scoped>
/*
colors: 
1. datk blue #264653
2. light blue #2a9d8f
3. light yellow #e9c46a 
4. light oragne #f4a261
5. dark orange #e76f51
*/
</style>
