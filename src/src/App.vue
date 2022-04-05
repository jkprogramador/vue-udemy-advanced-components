<template>
    <p class="display-4 text-success">Hey!</p>
    <greetingItem :age="age"></greetingItem>
    <userItem
        :age="age"
        :ageChangedFn="updateAgeCb"
        @onAgeChanged="updateAge"
    ></userItem>
    <form-item>
        <template v-slot:help>
            <p>{{ help }}</p>
        </template>
        <template v-slot:fields>
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
        </template>
        <template v-slot:buttons>
            <button type="submit" class="btn btn-primary btn-lg">Submit</button>
        </template>

        <p>Dummy text</p>
    </form-item>

    <form-item>
        <template v-slot:help>
            <p>Contact help text</p>
        </template>
        <template v-slot:fields>
            <div class="form-floating mb-3">
                <input
                    id="name"
                    type="text"
                    class="form-control"
                    placeholder="Name"
                />
                <label for="name">Name</label>
            </div>
            <div class="form-floating mb-3">
                <input
                    id="message"
                    class="form-control"
                    type="text"
                    placeholder="Message"
                />
                <label for="message">Message</label>
            </div>
        </template>
        <template v-slot:buttons>
            <button type="submit" class="btn btn-primary btn-lg">Submit</button>
        </template>
    </form-item>
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
            help: "This is some help text",
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