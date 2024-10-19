<template>
    <div className="container">
        <button @click="deleteUser(index)" >delete user ❌</button>
        <h3>{{ user.name }}</h3>
        <p>{{ user.email }} - <b>{{ user.pass }}</b></p>
    </div>
</template>

<script>
export default {
    props: {
        user: {
            type: Object,
            required: true
        },
        index: {
            type: Number,
            required: true
        },
        deleteUser: {
            type: Function,
            required: true
        }
    }
}
</script>

<style scoped>
button {
    cursor: pointer;
    background-color: gold;
    border: 1px solid black;
    border-radius: 5px;
    padding: 5px 5px;
   margin-left: 190px;
}

</style>
