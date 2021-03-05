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
    background-color: #f59c2f;
    text-align: center;
    padding: 20px;
}
</style>
