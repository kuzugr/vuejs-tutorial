<template>
  <button id="c-button" v-bind:disabled="!canBuy">購入</button>
</template>

<script>
export default {
  name: 'cButton',
  el: '#c-button',
  data () {
    return {
      canBuy: false
    }
  }
}
</script>
