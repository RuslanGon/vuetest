<template>
  <h1>CRIPTO</h1>
  <Input :changeAmount="changeAmount"/>
  {{ amount }}
  <div class="selectors">
    <Selector />
    <Selector />
  </div>

</template>

<script>
import Input from './components/Input.vue';
import Selector from './components/Selector.vue';
export default {
  components: { Input, Selector },
  data() {
    return {
      amount: 0
    }
  },
  methods: {
    changeAmount(val) {
      this.amount = val
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