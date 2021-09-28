<template>
  <img alt="Got fluid" src="./assets/GotFluid.png">
  <h1>Paste your Ethereum address</h1>
  <input @keyup.enter="redirect" placeholder="0x..." v-model="address">
  <button @click="redirect">Check</button>
  <br/><br/>
  <br/><br/>
  <p><i>Made by the community</i></p>
</template>

<script>
export default {
  name: 'App',
  data() {
    return {
      address: null,
    }
  },
  methods: {
    redirect() {
      if (!this.address)
        return

      const url = "https://arbiscan.io/token/0x876ec6be52486eeec06bc06434f3e629d695c6ba?a=" + this.address
      window.open(url, '_blank')
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
