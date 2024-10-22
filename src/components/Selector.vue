<template>
    <ul>
        <li>Bitcoin</li>
        <li>ETH</li>
        <li>USDT</li>
    </ul>
</template>

<script>
export default {

}
</script>

<style scoped>
ul {
    list-style: none;
    width: 200px;
    padding: 0;
    border-radius: 3px;
    border: 3px solid gold;
    margin-left: 540px;
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