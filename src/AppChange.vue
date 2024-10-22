<template>
  <div>
    <h1>CRYPTO</h1>
    <Input :changeAmount="changeAmount"/>
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
      cryptoSecond: ''  
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
