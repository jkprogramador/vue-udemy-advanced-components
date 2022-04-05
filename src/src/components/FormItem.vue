<template>
    <form>
        <div class="row mt-5">
            <div class="col-12 help">
                <slot name="help"></slot>
            </div>
            <div class="col-md-7 fields">
                <slot name="fields"></slot>
            </div>
            <div class="col-12 buttons">
                <slot name="buttons"></slot>
            </div>

            <slot></slot>
        </div>
    </form>
</template>

<script>
export default {
    name: "FormItem",
};
</script>

<style>
</style>