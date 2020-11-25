<template>
<div id="app">
    <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
    <Header/>
    <Home class="minheight" msg="Welcome to Gagan Vue.js App"/>
    <Footer/>
</div>
</template>

<script>
import Vue from 'vue';
import CoreuiVue from '@coreui/vue';
Vue.use(CoreuiVue);

import Home from './components/Home'

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
  color: #2c3e50;
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
.minheight {
  min-height: 100vh
}

</style>
