<template>
    <ul>
      <li @click="setCrypto('BTC')" :class="cryptoNow === 'BTC' ? 'active' : ''">Bitcoin</li>
      <li @click="setCrypto('ETH')" :class="cryptoNow === 'ETH' ? 'active' : ''">ETH</li>
      <li @click="setCrypto('USDT')" :class="cryptoNow === 'USDT' ? 'active' : ''">USDT</li>
    </ul>
  </template>
  
  <script>
  export default {
    props: {
      setCrypto: {
        type: Function,
        required: true
      },
      cryptoNow: {
        type: String,
        required: true
      }
    }
  }
  </script>
  
  <style scoped>
  ul {
    list-style: none;
    width: 170px;
    padding: 0;
    border-radius: 3px;
    border: 3px solid gold;
    margin-top: 20px;
  }
  
  li {
    display: block;
    background-color: transparent;
    padding: 20px 0;
  }
  
  li:hover, li:active {
    cursor: pointer;
    background-color: rgb(253, 242, 180);
    color: black;
  }
  
  .active {
    background-color: gold;  
    color: black;
  }
  </style>
  