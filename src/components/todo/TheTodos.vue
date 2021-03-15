<template>
    <div class="todos">
        <todos-nav></todos-nav>
        <component :is="selectedTab"></component>
    </div>
</template>

<script>
import TodosNav from '../navigation/TodosNav';
import StoredTodos from './StoredTodos.vue';
import AddTodo from './AddTodo.vue';

export default {
    components: {
        TodosNav,
        StoredTodos,
        AddTodo
    },
    data() {
        return {
            selectedTab: 'stored-todos',
            storedTodos: []
        };
    },
    methods: {
        switchTabHandler(tab) {
            this.selectedTab = tab;
        },
        addTodo(todo) {
            this.storedTodos.unshift(todo);
            this.selectedTab = 'stored-todos';
        }
    },
    provide() {
        return {
            switchTab: this.switchTabHandler,
            storedTodos: this.storedTodos,
            addTodo: this.addTodo
        };
    }
};
</script>

<style scoped>
.todos {
    max-width: 700px;
    margin: 50px auto;
    padding: 0 15px;
}
</style>
