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

import { v4 as uuidv4 } from 'uuid';

export default {
    components: {
        TodosNav,
        StoredTodos,
        AddTodo
    },
    data() {
        return {
            selectedTab: 'stored-todos',
            storedTodos: [
                {
                    id: uuidv4(),
                    title: 'Dog',
                    description: 'walk the dog',
                    completed: false
                },
                {
                    id: uuidv4(),
                    title: 'School',
                    description: 'go to school',
                    completed: false
                }
            ]
        };
    },
    methods: {
        switchTabHandler(tab) {
            this.selectedTab = tab;
        }
    },
    provide() {
        return {
            switchTab: this.switchTabHandler,
            storedTodos: this.storedTodos
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
