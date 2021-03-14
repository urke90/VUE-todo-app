<template>
    <li class="todo__item">
        <h3 class="todo__title">{{ title }}</h3>
        <p class="todo__description" :class="completedTodoMode">
            {{ description }}
        </p>
        <br />
        <div class="todo__actions">
            <label for="todo__completed">
                Completed
                <input
                    type="checkbox"
                    name="completed"
                    class="todo__input"
                    v-model="isCompleted"
                />
            </label>
            <base-button @click="removeTodo(id)" className="btn btn--secondary">
                Remove
            </base-button>
        </div>
    </li>
</template>

<script>
export default {
    props: {
        title: {
            type: String,
            required: true
        },
        description: {
            type: String,
            required: true
        },
        id: {
            type: String,
            required: true
        }
    },
    data() {
        return {
            isCompleted: false
        };
    },
    computed: {
        completedTodoMode() {
            return { 'todo__description--completed': this.isCompleted }
        }
    },
    inject: ['removeTodo']
};
</script>

<style scoped>
.todo__item {
    border-radius: 3px;
    padding: 20px;
    background-color: #e76f51;
    border-radius: 3px;
    margin-bottom: 10px;
}
.todo__title {
    text-transform: uppercase;
    font-weight: 700;
    margin-bottom: 10px;
}
.todo__description {
    font-size: 18px;
}
.todo__actions {
    display: flex;
    justify-content: space-between;
    align-items: center;
}
.todo__input {
    margin-left: 10px;
}
.todo__description--completed {
    text-decoration: line-through;
}
</style>
