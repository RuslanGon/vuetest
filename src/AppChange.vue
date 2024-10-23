<template>
  <div>
    <h1>C R Y P T O</h1>
    <Input :changeAmount="changeAmount" :convert="convert" :favourite="favourite"/>
    <p v-if="error != ''">{{ error }}</p>
    <p class="result"v-if="result !== 0">{{ result }}</p>
{{ favs }}
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
      error: '',
      result: 0,
      favs: []
    }
  },
  methods: {
    changeAmount(val) {
      this.amount = parseFloat(val); // Убедимся, что amount - это число
    },
    setCryptoFirst(val) {
      this.cryptoFirst = val;
    },
    setCryptoSecond(val) {
      this.cryptoSecond = val;
    },
    async convert() {
      if (this.amount <= 0 || isNaN(this.amount)) {
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

      try {
        // Ждём готовности конвертера
        await convert.ready();

        // Логируем выбранные валюты
        console.log(`Converting ${this.cryptoFirst} to ${this.cryptoSecond}`);

        // Получаем соответствующий метод для конвертации
        const conversionMethod = convert[this.cryptoFirst][this.cryptoSecond];

        // Проверяем наличие метода конвертации
        if (typeof conversionMethod !== 'function') {
          this.error = 'Conversion rate is invalid';
          return;
        }

        // Выполняем конвертацию
        const rate = await conversionMethod(1);

        // Логируем курс для проверки
        console.log(`Rate for ${this.cryptoFirst} to ${this.cryptoSecond}:`, rate);

        // Проверяем, что курс является числом
        if (isNaN(rate)) {
          this.error = 'Conversion rate is invalid';
          return;
        }

        // Рассчитываем результат
        this.result = rate * this.amount;
      } catch (err) {
        this.error = 'Error fetching conversion rate';
        console.error(err);
      }
    },
    favourite() {
this.favs.push({
  form: this.cryptoFirst,
  to: this.cryptoSecond
})
    }
  }
}
</script>

<style scoped>
.result {
  font-size: 24px;
}
.selectors {
  display: flex;
  margin-left: 440px;
  gap: 20px;
}
</style>
