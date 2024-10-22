<template>
  <div>
    <h1>C R Y P T O</h1>
    <Input :changeAmount="changeAmount" :convert="convert"/>
    <p v-if="error != ''">{{ error }}</p>
    <div class="selectors">
      <Selector :setCrypto="setCryptoFirst"/>
      <Selector :setCrypto="setCryptoSecond"/>
    </div>
  </div>
</template>

<script>
import Input from './components/Input.vue';
import Selector from './components/Selector.vue';

export default {
  components: { Input, Selector },
  data() {
    return {
      amount: 0,
      cryptoFirst: '',   
      cryptoSecond: '',
      error: ''
    }
  },
  methods: {
    changeAmount(val) {
      this.amount = val;
    },
    setCryptoFirst(val) {
      this.cryptoFirst = val;
    },
    setCryptoSecond(val) {
      this.cryptoSecond = val;
    },
    convert() {
      if (this.amount <= 0) {
        this.error = 'enter a number greater than 0'
        return
      }else if (this.setCryptoFirst == this.setCryptoSecond) {
        this.error = 'select currency'
        return
      }

    }
  }
}
</script>

<style scoped>
.selectors {
  display: flex;
  margin-left: 440px;
  gap: 20px;
}
</style>
