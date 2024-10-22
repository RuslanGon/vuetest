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
import CryptoConvert from 'crypto-convert';
import Input from './components/Input.vue';
import Selector from './components/Selector.vue';

const convert = new CryptoConvert();

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
    async convert() {
      if (this.amount <= 0) {
        this.error = 'Enter a number greater than 0';
        return;
      } else if (this.cryptoFirst === '' || this.cryptoSecond === '') {
        this.error = 'Select both currencies';
        return;
      } else if (this.cryptoFirst === this.cryptoSecond) {
        this.error = 'Select different currencies';
        return;
      }
      this.error = ''; 

      await convert.ready()
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
