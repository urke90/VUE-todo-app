<template>
    <base-modal v-if="invalidInput" @close="closeErrorModalHandler">
        <template #header>
            <h2>Error creating todo</h2>
        </template>
        <template #default>
            <p>Please enter valid data.</p>
        </template>
        <template #actions>
            <base-button
                @click="closeErrorModalHandler"
                class="btn btn--secondary"
            >
                Close
            </base-button>
        </template>
    </base-modal>
    <form @submit.prevent="getFormData" class="add-todo__form">
        <div class="form__group">
            <label class="add-todo__label" for="title">
                Title
            </label>
            <input
                type="text"
                name="title"
                id="title"
                placeholder="Title"
                ref="title"
            />
        </div>
        <div class="form__group">
            <label class="add-todo__label" for="description">
                Description
            </label>
            <textarea
                name="description"
                id="description"
                cols="30"
                rows="5"
                placeholder="Description"
                ref="description"
            ></textarea>
        </div>
        <base-button type="submit" class="btn btn--secondary">
            Add Todo
        </base-button>
    </form>
</template>

<script>
import { v4 as uuidv4 } from 'uuid';
export default {
    data() {
        return {
            invalidInput: false
        };
    },
    methods: {
        closeErrorModalHandler() {
            this.invalidInput = false;
        },
        getFormData() {
            const title = this.$refs.title.value;
            const description = this.$refs.description.value;
            if (title.trim() == '' || description.trim() == '') {
                this.invalidInput = true;
                return;
            }
            const todo = {
                id: uuidv4(),
                title,
                description
            };
            this.addTodo(todo);
        }
    },
    inject: ['addTodo']
};
</script>

<style scoped>
.add-todo__label {
    margin-bottom: 10px;
    text-transform: uppercase;
    font-weight: 600;
}
.form__group {
    display: flex;
    flex-direction: column;
    margin-bottom: 20px;
}
.add-todo__form {
    position: relative;
    background-color: #e76f51;
    padding: 20px;
    border-radius: 3px;
}
input,
textarea {
    border-radius: 3px;
    outline: none;
    border: none;
    padding: 7px;
    resize: none;
}
input::placeholder,
textarea::placeholder {
    color: #264653;
}
</style>
