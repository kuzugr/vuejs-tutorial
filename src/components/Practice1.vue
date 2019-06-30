<template>
  <div id="app">
    <bButton />
    <cButton />
    <p>
      {{ items[0].name }}: {{ items[0].price }} × {{ items[0].quantity }}
    </p>
    <p>小計: {{ totalPrice | numberWithDelimiter }}円</p>
    <p>合計(税込): {{ totalPriceWithTax | numberWithDelimiter }}円</p>
    <p v-show="!canBuy"></p>
  </div>
</template>

<script>
import bButton from './practice1/bButton'
import cButton from './practice1/cButton'
var items = [
  {
    name: '鉛筆',
    price: 300,
    quantity: 0
  },
  {
    name: 'ノート',
    price: 400,
    quantity: 0
  },
  {
    name: '消しゴム',
    price: 500,
    quantity: 0
  }
]
export default {
  name: 'Practice1',
  components: {bButton, cButton},
  data () {
    return {
      items: items
    }
  },
  filters: {
    numberWithDelimiter: function (value) {
      if (!value) {
        return '0'
      }
      return value.toString().replace(/(\d)(?=(\d{3})+$)/g, '$1,')
    }
  },
  computed: {
    totalPrice: function () {
      return this.items.reduce(function (sum, item) {
        return sum + (item.price * item.quantity)
      }, 0)
    },
    totalPriceWithTax: function () {
      return Math.floor(this.totalPrice * 1.08)
    }
  }
}
</script>
