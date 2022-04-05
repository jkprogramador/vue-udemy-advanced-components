<template>
    <p class="display-4 text-success">Hey!</p>
    <greetingItem></greetingItem>
    <userItem :age="age"></userItem>
</template>

<script>
import GreetingItem from "./components/GreetingItem.vue";
import UserItem from "./components/UserItem.vue";

export default {
    name: "App",
    components: {
        GreetingItem,
        UserItem,
    },
    data() {
        return {
            age: 20,
        };
    },
};
</script>