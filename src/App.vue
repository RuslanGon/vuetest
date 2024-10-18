<template>
  <form action="" @submit.prevent="sendData">
    <input type="text" placeholder="name" v-model="userName">
    <input type="password" placeholder="password" v-model="userPass">
    <input type="email" placeholder="email" v-model="userEmail">
    <p className="error">{{ error }}</p>
    <button>Send</button>
  </form>
  <p>{{ users }}</p>

</template>

<script>
export default {
  data() {
    return {
      users: [],
      error: '',
      userName: '',
      userPass: '',
      userEmail: '',
    }
  },
  methods: {
    sendData() {
      if(this.userName == ''){
        this.error = 'name is required'
        return
      }
      this.users.push({
        name: this.userName,
        pass: this.userPass,
        email: this.userEmail
      })
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
