<template>
    <nav class="todos__nav">
        <i class="fas fa-bars nav__menu" @click="toggleNavHandler"></i>
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
        <ul class="nav__list nav__list--mobile" :class="toggledNav">
            <li class="nav__item">
                <base-button className="nav__link">
                    Add Todo
                </base-button>
            </li>
            <li class="nav__item">
                <base-button className="nav__link">
                    Todos List
                </base-button>
            </li>
        </ul>
    </nav>
</template>

<script>
// TODO choose colors for app, split nav items into components, create button component
export default {
    data() {
        return {
            isOpened: false
        };
    },
    methods: {
        toggleNavHandler() {
            this.isOpened = !this.isOpened;
        }
    },
    computed: {
        toggledNav() {
            return { opened: this.isOpened };
        }
    }
};
</script>

<style scoped>
.mr-10 {
    margin-right: 10px;
}
.todos__nav {
    background-color: #2a9d8f;
    display: flex;
    position: relative;
    padding: 15px;
    margin-bottom: 50px;
    min-height: 60px;
}

.nav__menu {
    font-size: 30px;
    color: #264653;
}

.nav__list {
    list-style-type: none;
}

.nav__list--desktop {
    display: none;
}

.nav__list--mobile {
    width: 100%;
    height: 0;
    display: none;
    background-color: #2a9d8f;
    position: absolute;
    text-align: center;
    top: 60px;
    left: 0;
}

.nav__list--mobile.opened {
    display: block;
    height: auto;
    transition: all 2s ease-in;
}

@media screen and (min-width: 420px) {
    .nav__menu {
        display: none;
    }
    .nav__list--desktop {
        display: flex;
        align-items: center;
    }
    .nav__list--mobile.opened {
        display: none;
    }
}
</style>
