<template>
  <form action="" @submit.prevent="sendData">
    <input type="text" placeholder="name" v-model="userName">
    <input type="password" placeholder="password" v-model="userPass">
    <input type="email" placeholder="email" v-model="userEmail">
    <p className="error">{{ error }}</p>
    <button>Send</button>
  </form>
  <!-- <p>{{ users }}</p> -->
  <div v-if="users.length == 0">
    <p className="container1">now is not user</p>
  </div>
  <div v-else-if="users.length == 1">
    <p className="container1">now is one user</p>
  </div>
  <div v-else-if="users.length == 2">
    <p className="container1">now is two user</p>
  </div>
  <User v-for="(el, index) in users" :key="index" :user="el" index="index" :deleteUser="deleteUser" />

</template>

<script>
import User from './components/User.vue'

export default {
  components: { User },
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
      if (this.userName == '') {
        this.error = 'name is required'
        return
      } else if (this.userPass == '') {
        this.error = 'password is required'
        return
      } else if (this.userEmail == '') {
        this.error = 'email is required'
        return
      }
      this.error = ''

      this.users.push({
        name: this.userName,
        pass: this.userPass,
        email: this.userEmail
      })

      this.userName = '';
      this.userPass = '';
      this.userEmail = '';
    },
    deleteUser(index) {
      this.users.splice(index, 1)
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

.container {
  margin-top: 10px;
  height: 100px;
  max-width: 300px;
  background-color: rgb(221, 216, 216);
  padding: 15px 15px;

}

button {
  background-color: green;
  cursor: pointer;
  width: 100px;
margin-left: 100px;
color: white;
}
</style>
