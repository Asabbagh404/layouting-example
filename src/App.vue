<template>
  <div id="app">
    <div id="nav">
      <router-link to="/">Home</router-link> |
      <router-link to="/about">About</router-link>
    </div>
    <component :is="currentPage"></component>
  </div>
</template>
<script>
import defaultLayout from '@/views/layout/defaultLayout.vue'
import noLayout from '@/views/layout/noLayout.vue'

export default {
  component: {
    defaultLayout,
    noLayout
  },
  computed: {
    currentPage() {
      return !this.$route.meta.layout ? defaultLayout : noLayout
    }
  }
}
</script>
<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;

  a {
    font-weight: bold;
    color: #2c3e50;

    &.router-link-exact-active {
      color: #42b983;
    }
  }
}
</style>
