<template>
  <button id="b-button" v-bind:title="loggedInButton">購入</button>
</template>

<script>
export default {
  name: 'bButton',
  el: '#b-button',
  data () {
    return {
      loggedInButton: 'ログイン済みのため購入できます。'
    }
  }
}
</script>
