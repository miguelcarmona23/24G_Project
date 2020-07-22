<template>
    <div id="app">
    <img style="width:140px; margin:14px;" src="./assets/24g_transparent.jpg"/>
    <h2>Miguel Carmona</h2>
    <VideoPlayer/>
</div>
</template>

<script>
import VideoPlayer from './components/VideoPlayer'

export default {
  name: 'App',
  components: {
    VideoPlayer
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}
</style>
