<template>
    <p class="display-4 text-success">Hey!</p>
    <greetingItem></greetingItem>
</template>

<script>
import GreetingItem from "./components/GreetingItem.vue";

export default {
    name: "App",
    components: {
        GreetingItem,
    },
};
</script>