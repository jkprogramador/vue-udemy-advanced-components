<template>
    <p class="display-4 text-success">Hey!</p>
    <greetingItem :age="age"></greetingItem>
    <userItem
        :age="age"
        :ageChangedFn="updateAgeCb"
        @onAgeChanged="updateAge"
    ></userItem>
    <form-item>
        <div class="col-12 help">
            <p>This is some help text</p>
        </div>
        <div class="col-md-7 fields">
            <div class="form-floating mb-3">
                <input
                    id="email"
                    type="text"
                    class="form-control"
                    placeholder="Email"
                />
                <label for="email">Email</label>
            </div>
            <div class="form-floating mb-3">
                <input
                    id="username"
                    class="form-control"
                    type="text"
                    placeholder="username"
                />
                <label for="username">Username</label>
            </div>
            <div class="form-floating mb-3">
                <input
                    id="password"
                    class="form-control"
                    type="text"
                    placeholder="password"
                />
                <label for="password">Password</label>
            </div>
        </div>
        <div class="col-12 buttons">
            <button type="submit" class="btn btn-primary btn-lg">Submit</button>
        </div>
    </form-item>

    <form-item />
</template>

<script>
import GreetingItem from "./components/GreetingItem.vue";
import UserItem from "./components/UserItem.vue";
import FormItem from "./components/FormItem.vue";

export default {
    name: "App",
    components: {
        GreetingItem,
        UserItem,
        FormItem,
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
        updateAgeCb(num) {
            this.age += num;
        },
    },
};
</script>