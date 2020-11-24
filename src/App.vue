<template>
<div id="app">
    <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
    <Home msg="Welcome to Gagan Vue.js App"/>
</div>
</template>

<script>
import Vue from 'vue';
import CoreuiVue from '@coreui/vue';
Vue.use(CoreuiVue);

import Home from './components/Home.vue'


export default {
  name: 'App',
  components: {
    Home,

  }
}
</script>


<style lang="scss" src="../node_modules/@coreui/coreui/scss/coreui.scss" />

<style>


#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

#list-users {
  margin: 0px;
  padding: 0px;
}
div {
  .top {
    margin-top: -160px;
  }
}

</style>
