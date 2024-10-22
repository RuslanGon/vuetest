<template>
    <ul>
        <li @click="selectItem('BTC')" :class="current == 'BTC' ? 'active' : ''">Bitcoin</li>
        <li @click="selectItem('ENT')" :class="current == 'ENT' ? 'active' : ''">ENT</li>
        <li @click="selectItem('USDT')" :class="current == 'USDT' ? 'active' : ''">USDT</li>
    </ul>
</template>

<script>
export default {
props: {
    setCrypto: {
        type: Function,
        required: true
    }
},
data() {
    return {
        current: ''
    }
},
methods: {
selectItem(val) {
    this.setCrypto(val),
    this.current = val
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