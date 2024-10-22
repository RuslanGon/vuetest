<template>
<input type="number" min="0" @input="changeAmount($event.target.value)">
</template>

<script>
export default {
props: {
    changeAmount: {
        type: Function,
        required: true
    }
}
}
</script>

<style scoped>
input {
    outline: none;
    border-radius: 17px;
    border: 0;
    padding: 10px 15px;
    background-color: aliceblue;
    font-size: 24px;
    width: 350px;
}
</style>