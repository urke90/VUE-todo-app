<template>
    <button :class="className">
        <slot></slot>
    </button>
</template>

<script>
export default {
    props: {
        className: {
            type: String,
            required: true
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
</style>