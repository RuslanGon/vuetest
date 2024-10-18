<template>
  <form action="" @submit.prevent="sendData">
    <input type="text" placeholder="name" v-model="userName">
    <input type="password" placeholder="password" v-model="userPass">
    <input type="email" placeholder="email" v-model="userEmail">
    <p className="error">{{ error }}</p>
    <button>Send</button>
  </form>
  <!-- <p>{{ users }}</p> -->
  <div className="container" v-for="(el, index) in users" :key="index">
    <h3>{{ el.name }}</h3>
  <p>{{ el.email}} - <b>{{ el.pass }}</b></p>
</div>

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
      } else  if(this.userPass== ''){
        this.error = 'password is required'
        return
      } else  if(this.userEmai == ''){
        this.error = 'email is required'
        return
      }
       this.error = ''
       
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

.container {
  margin-top: 10px;
height: 100px;
max-width: 300px;
background-color: rgb(221, 216, 216);
padding: 15px 15px;
}
</style>
