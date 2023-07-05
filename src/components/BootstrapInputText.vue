<template>
    <div class="mb-3">
        <label class="form-label card-text mb-2" :for="label">{{label}}</label>
        <input type="text" :id="label" class="form-control mb-2">
        <slot></slot>
    </div>
</template>

<script>
    export default {
        name: "BootstrapInputText",
        props: ["label","valuee"]
    }
</script>

<style scoped>

</style>