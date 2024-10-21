<template>
  <div class="wrapper">
    <h1>Weather Application</h1>
    <p>Find out the weather in your city</p>
    <input type="text" placeholder="enter yuor city">
    <button>get weather</button>
  </div>
</template>

<script>

</script>


<style scoped>
.wrapper {
  width: 900px;
  height: 500px;
  border-radius: 50px;
  background-color: rgb(48, 46, 46);
  color: white;
  padding: 20px;
  text-align: center;
}

.wrapper h1 {
  margin-top: 50px;
  padding-bottom: 20px;
}

.wrapper input {
  margin-top: 30px;
  background-color: transparent;
  border: 0;
  border-bottom: 2px solid gold;
  color: white;
  font-size: 14px;
  padding: 5px 8px;
  outline: none;
}

.wrapper input:focus {
  border-bottom-color: white;
}
</style>
