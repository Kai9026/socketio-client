<template>
  <div id="app">
    <img src="./assets/logo.png">
    <router-view/>
  </div>
</template>

<script>
export default {
  name: 'App',
  data () {
    return {
      message: ''
    }
  },
  sockets: {
    connect: function () {
      console.log('socket connected')
    },
    message: function (val) {
      alert('Mensaje de bienvenida: ' + val.message)
      this.message = val.message
      console.log('this method fired by socket server. eg: io.emit("customEmit", data)')
    }
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
