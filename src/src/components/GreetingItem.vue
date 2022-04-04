<template>
    <p class="display-2">{{ msg }}</p>
</template>

<style scoped>
p {
    color: red;
}
</style>

<script>
export default {
    name: "GreetingItem",
    data() {
        return {
            msg: "Hello World!",
        };
    },
};
</script>