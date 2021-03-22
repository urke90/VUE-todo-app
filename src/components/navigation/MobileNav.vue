<template>
    <div>
        <i class="fas fa-bars nav__menu" @click="toggleNavHandler"></i>
        <ul class="nav__list nav__list--mobile" :class="toggledNav">
            <li>
                <base-button
                    @click="switchTab('stored-todos')"
                    class="nav__link"
                >
                    Todos List
                </base-button>
            </li>
            <li>
                <base-button @click="switchTab('add-todo')" class="nav__link">
                    Add Todo
                </base-button>
            </li>
        </ul>
    </div>
</template>

<script>
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
    },
    inject: ['switchTab']
};
</script>

<style scoped>
.nav__menu {
    font-size: 30px;
    color: #264653;
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
