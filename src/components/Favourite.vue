<template>
<h2>Options to favorites</h2>
<div v-for="(el, index) in favs" key="index">
<span>{{ el.form }}</span>
<span>{{ el.to }}</span>
</div>
</template>

<script>
export default {
props: {
    favs: {
        type: Array,
        required: true
    }
}
}
</script>

<style scoped>
div {
    margin-left: 583px;
    display: flex;
    gap: 20px;
}
h2 {
    color: white;
}
</style>