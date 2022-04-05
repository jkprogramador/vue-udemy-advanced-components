<template>
    <p class="display-5">The user is {{ age }} years old</p>
</template>

<script>
export default {
    name: "UserItem",
    props: ["age"],
};
</script>