<template>
    <h1>Home Page</h1>
</template>

<script>
export default {
    name: "HomeItem",
    unmounted() {
        window.alert("HomeItem component unmounted.");
    },
    activated() {
        window.alert("HomeItem component activated.");
    },
    deactivated() {
        window.alert("HomeItem component deactivated.");
    },
};
</script>

<style>
</style>