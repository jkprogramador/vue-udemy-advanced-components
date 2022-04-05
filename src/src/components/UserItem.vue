<template>
    <button class="btn btn-primary btn-lg" type="button" @click="onClickAge">
        Increment age Event
    </button>

    <p class="display-5">The user is {{ age }} years old</p>
    <p class="display-5">Age doubled: {{ ageDoubled }}</p>

    <button
        class="btn btn-secondary btn-lg"
        type="button"
        @click="ageChangedFn(3)"
    >
        Increment age Callback
    </button>
</template>

<script>
export default {
    name: "UserItem",
    props: {
        age: {
            type: Number,
            // required: true,
            // default: 20,
            validator(value) {
                return value < 130;
            },
        },
        ageChangedFn: Function,
    },
    emits: ["onAgeChanged"],
    computed: {
        ageDoubled() {
            return this.age * 2;
        },
    },
    methods: {
        onClickAge() {
            this.$emit("onAgeChanged", 3);
        },
    },
};
</script>