<template>
  <button v-bind:title="loggedInButton">購入</button>
</template>

<script>
export default {
  name: 'bButton',
  data () {
    return {
      loggedInButton: 'ログイン済みのため購入できます。'
    }
  }
}
</script>
