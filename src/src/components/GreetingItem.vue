<template>
    <p class="display-2">{{ msg }}</p>
</template>

<style scoped lang="scss">
$color: red;
p {
    color: $color;
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