<template>
  <div id="app">
    <img src="./assets/logo.png">
    <hello></hello>
  </div>
</template>

<script>
import Hello from './components/Hello'

export default {
  name: 'app',
  components: {
    Hello
  },
  created () {
    const postData = {
      grant_type: 'password',
      client_id: 2,
      client_secret: 'zTAsKOickKnNHh0J9TzV3BkDgqDHUzrpkWSlAsLR',
      username: 'aaa',
      password: '1234',
      scope: ''
    }
    this.$http.post('http://127.0.0.1:8000/oauth/token', postData)
      .then(response => {
        console.log(response)
      })
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
