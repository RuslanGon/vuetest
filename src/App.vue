
<template>
<form action="">
<input type="text" placeholder="name">
<input type="password" placeholder="password"> 
<input type="email" placeholder="email">
</form>
</template>

<script>
export default {
  data() {
    return {
      info: 'Title',
      someInfo: "Anons message"
    }
  },
  methods: {
    userData() {
      this.info = 'some info'
      this.someInfo = 'Hello Ruslan'

    }
  }
}
</script>

<style scoped>

form {
  display: flex;
  flex-direction: column;
  max-width: 300px;
  gap: 10px;
  border: 2px solid red;
  padding: 15px 15px;
}
input {
  height: 30px;

}

</style>
