<template>
  <div id="app">
    <Loader msg="Welcome to Your Vue.js App"/>
  </div>
</template>

<script>
import Loader from './components/Loader'

export default {
  name: 'App',
  components: {
      Loader
  }
}
</script>

<style>
body {
    height: 100vh;
    margin: 0;
    padding: 0;
    font-family:"Microsoft YaHei",微软雅黑,"Microsoft JhengHei",华文细黑,STHeiti,MingLiu;
    background: rgba(0, 109, 174, 1);
}
#app {
    position: relative;
    height: 100%;
}
p {
    margin: 0;
}
</style>
