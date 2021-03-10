<template>
    <header>
        <h2>
            {{ title }}
        </h2>
    </header>
</template>

<script>
export default {
    props: {
        title: {
            type: String,
            required: true
        }
    }
};
</script>

<style scoped>
h2 {
    background-color: #e76f51;
    text-align: center;
    padding: 20px;
}
</style>
