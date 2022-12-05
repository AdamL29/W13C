<template>
  <div id="app">
    <songList/>
    <playList/>
    <pageBody/>
  </div>
</template>

<script>
import songList from '@/components/songs.vue';
import playList from '@/components/playlist.vue';
import pageBody from '@/components/page.vue';

export default {
  name: 'App',
  components: {
    songList,
    playList,
    pageBody,
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
