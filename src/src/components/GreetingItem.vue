<template>
    <p v-if="age >= 25" class="display-2">{{ msg }}</p>
    <p v-else>You must 25 years or older to view this message.</p>
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
    props: ["age"],
};
</script>