<template>
  <div class="bg-default min-h-screen">
    <Sidebar :toggleSidebar="toggleSidebar"/>
    <div class="">
      <Header @toggleSidebar="sidebar"/>
    </div>
    <router-view/>
  </div>
</template>

<script>
import { Header, Sidebar } from './components/layouts'
export default {
  components: {
    Header,
    Sidebar
  },
  data () {
    return {
      toggleSidebar: false,
    }
  },
  methods: {
    sidebar (val) {
      console.log(val)
      this.toggleSidebar = val
    }
  }
}
</script>

<style>
body {
  font-family: 'Poppins', sans-serif !important;
}
#app {
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
}
</style>
