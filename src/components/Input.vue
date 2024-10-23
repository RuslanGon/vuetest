<template>
<input type="number" min="0" @input="changeAmount($event.target.value)"><br>
<button @click="convert()">Convert</button>
<button class="fav" @click="favourite()">Favorites</button>

</template>

<script>
export default {
props: {
    changeAmount: {
        type: Function,
        required: true
    },
    convert: {
        type: Function,
        required: true
    },
    favourite: {
        type: Function,
        required: true
    }
}
}
</script>

<style scoped>
.fav {
    margin-left: 20px;
}
button{
    margin-top: 20px;
    padding: 10px 15px;
    border-radius: 7px;
    font-size: 20px;
    cursor: pointer;
    border: 3px solid gold;
    text-transform: uppercase;
}
button:hover {
    border: 3px solid white;
    background-color: gold;
    color: black;
}
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