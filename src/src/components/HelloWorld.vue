<template>
    <div>
        <!-- Slot properties allow you to send data to parent scope -->
        <slot :user="user" :favorites="favorites"></slot>
    </div>
</template>

<script>
export default {
    name: "HelloWorld",
    data() {
        return {
            user: {
                name: "John",
                age: 25,
            },
            favorites: ["Pizza", "Marbles", "Birds"],
        };
    },
};
</script>

<style>
</style>