<template>
    <ul class="nav__list nav__list--desktop">
        <li class="nav__item mr-10">
            <base-button className="btn">
                Add Todo
            </base-button>
        </li>
        <li class="nav__item">
            <base-button className="btn btn--secondary">
                Todos List
            </base-button>
        </li>
    </ul>
</template>

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
