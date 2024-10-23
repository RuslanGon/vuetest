<template>
<h2>Options to favorites</h2>
<div @click="getFormFavs(index)" v-for="(el, index) in favs" key="index">
<span>{{ el.from }}</span>
<span>{{ el.to }}</span>
</div>
</template>

<script>
export default {
props: {
    favs: {
        type: Array,
        required: true
    },
    getFormFavs: {
        type: Function,
        required: true
    }
}
}
</script>

<style scoped>
div:hover {
    cursor: pointer;
    color: gold;
}
div {
    margin-left: 500px;
    display: flex;
    gap: 170px;
}
h2 {
    color: white;
}
</style>