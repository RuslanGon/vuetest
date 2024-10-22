<template>
  <h1>CRIPTO</h1>
  <Input />
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
}
</script>

<style scoped>
.selectors {
  display: flex;
margin-left: 440px;
gap: 20px;


}
</style>