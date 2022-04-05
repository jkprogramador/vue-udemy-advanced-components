<template>
    <p class="display-4 text-success">Hey!</p>
    <greetingItem :age="age"></greetingItem>
    <userItem :age="age" @onAgeChanged="updateAge"></userItem>
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
    methods: {
        updateAge(num) {
            this.age += num;
        },
    },
};
</script>