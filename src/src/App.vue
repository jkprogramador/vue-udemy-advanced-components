<template>
    <!-- 'v' is an alias for the slot properties. It represents all properties bound to slot -->
    <!-- Alternative syntax: #default="{ user }" where #: shorthand for v-slot, 'default' is a name for the slot, { user } destructures the properties object -->
    <hello-world v-slot="v">
        <p>Hello {{ v.user.name }}.</p>
        <p>Favorites are:</p>
        <ul>
            <li v-for="(favorite, index) in v.favorites" :key="index">
                {{ index }}. {{ favorite }}
            </li>
        </ul>
    </hello-world>

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

    <div class="row my-5">
        <div class="col">
            <select class="form-select" v-model="componentName">
                <option value="HomeItem">Home</option>
                <option value="AboutItem">About</option>
            </select>

            <keep-alive>
                <component :is="componentName"></component>
            </keep-alive>
        </div>
    </div>
</template>

<script>
import GreetingItem from "./components/GreetingItem.vue";
import UserItem from "./components/UserItem.vue";
import FormItem from "./components/FormItem.vue";
import HomeItem from "./components/HomeItem.vue";
import AboutItem from "./components/AboutItem.vue";
import HelloWorld from "./components/HelloWorld.vue";

export default {
    name: "App",
    components: {
        GreetingItem,
        UserItem,
        FormItem,
        HomeItem,
        AboutItem,
        HelloWorld,
    },
    data() {
        return {
            age: 20,
            help: "This is some help text",
            componentName: "HomeItem",
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