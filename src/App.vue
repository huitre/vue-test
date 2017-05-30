<template>
  <div id="app">
    <router-view
      keep-alive
      transition
      transition-mode="out-in">
    </router-view>
  </div>
</template>

<script>
export default {
  name: 'app'
}
</script>

<style>
html {
  font-size: 16px;
}
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin: auto;
  max-width: calc(1000px - 320px);
  box-shadow: 1px 1px 3px rgba(0, 0, 0, 0.3);
}

.n82 a, .n06 a, .n81 a {
  color: #003872;
  cursor: pointer;
}

.n82 a:hover, .n06 a:hover, .n81 a:hover {
  color: #ff9d0b;
}



h2 {
  font-family: MuseoSlab500,Trebuchet MS,Arial,Helvetica,sans-serif;
  font-size: 2.25rem;
  line-height: 1.28571;
  margin-bottom: 15px;
  text-align: left;
}
</style>
