
<template>
<h3>{{ info }}</h3>
<p>{{ someInfo }}</p>
<button type="button" @click="userData()">Send</button>

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

h3 {
  font-size: 24px;
  font-weight: lighter;
  color: gold;
}
p {
font-size: 20px;
}

</style>
