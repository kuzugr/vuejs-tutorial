<template>
  <button v-bind:disabled="!this.$parent.canBuy">購入</button>
</template>

<script>
export default {
  name: 'cButton'
}
</script>
