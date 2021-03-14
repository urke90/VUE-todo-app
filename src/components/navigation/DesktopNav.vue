<template>
    <ul class="nav__list nav__list--desktop">
        <li class="mr-10">
            <base-button @click="switchTab('stored-todos')" className="btn">
                Todos List
            </base-button>
        </li>
        <li>
            <base-button
                @click="switchTab('add-todo')"
                className="btn btn--secondary"
            >
                Add Todo
            </base-button>
        </li>
    </ul>
</template>

<script>
export default {
    inject: ['switchTab']
};
</script>

<style scoped>
.nav__list--desktop {
    display: none;
}

.mr-10 {
    margin-right: 10px;
}

@media screen and (min-width: 420px) {
    .nav__list--desktop {
        display: flex;
        align-items: center;
    }
}
</style>
