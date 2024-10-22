<template>
    <ul>
        <li @click="setCrypto('BTC')">Bitcoin</li>
        <li @click="setCrypto('ENT')">ETH</li>
        <li @click="setCrypto('USDT')">USDT</li>
    </ul>
</template>

<script>
export default {
props: {
    setCrypto: {
        type: Function,
        required: true
    }
}
}
</script>

<style scoped>
ul {
    list-style: none;
    width: 170px;
    padding: 0;
    border-radius: 3px;
    border: 3px solid gold;
    margin-top: 20px;
}

li {
    display: block;
    background-color: transparent;
    padding: 20px 0;
}

li:hover, li:active {
    cursor: pointer;
    background-color: rgb(253, 242, 180);
    color: black;
}
</style>