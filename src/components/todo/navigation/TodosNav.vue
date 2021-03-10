<template>
    <nav class="todos__nav">
        <i class="fas fa-bars nav__menu" @click="toggleNavHandler"></i>
        <ul class="nav__list nav__list--desktop">
            <li class="nav__item mr-10">
                <button class="btn">
                    Add Todo
                </button>
            </li>
            <li class="nav__item">
                <button class="btn btn--secondary">
                    Todos List
                </button>
            </li>
        </ul>
        <ul class="nav__list nav__list--mobile" :class="toggledNav">
            <li class="nav__item">
                <button class="nav__link">
                    Add Todo
                </button>
            </li>
            <li class="nav__item">
                <button class="nav__link">
                    Todos List
                </button>
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
.btn {
    background-color: #e76f51;
    border: 1px solid #e76f51;
    outline: none;
    color: #264653;
    text-transform: uppercase;
    border: none;
    padding: 8px 16px;
    border-radius: 5px;
    font-weight: 600;
    cursor: pointer;
}
.btn--secondary {
    background: transparent;
    color: #264653;
    border: 1px solid #264653;
}
.btn--secondary:hover {
    background: #264653;
    color: #e76f51;
    border: 1px solid #264653;
}
button.nav__link {
    width: 100%;
    padding: 10px;
    background-color: transparent;
    border: 3px solid #2a9d8f;
    outline: none;
    text-transform: uppercase;
    color: #264653;
    font-weight: 600;
}
button.nav__link:hover {
    border: 3px solid #e76f51;
    background-color: #e76f51;
}

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
    display: none;
    background-color: #2a9d8f;
    position: absolute;
    text-align: center;
    top: 60px;
    left: 0;
}

.nav__list--mobile.opened {
    display: block;
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
