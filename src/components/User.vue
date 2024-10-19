<template>
    <div className="container">
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
        }
    }
}
</script>

<style></style>
