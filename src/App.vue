<template>
<div id="app">
  <el-container>
    <el-header>
      <Header></Header>
    </el-header>
    <el-container>
      <el-aside width="12%">
        <Aside></Aside>
      </el-aside>
      <el-main>
        <Main></Main>
      </el-main>
    </el-container>
    <el-footer>
      <Footer></Footer>
    </el-footer>
  </el-container>
</div>
</template>

<script>
import Aside from './Aside'
import Header from './Header'
import Footer from './Footer'
import Main from './App_Main'

export default {
  name: 'App',
  components: {
    Aside,
    Header,
    Main,
    Footer
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
  margin-top: 0px;
}
</style>

<style scoped>
.el-header {
  background-color: #CEF7BB;
  color: #333;
  text-align: center;
  line-height: 60px;
}

.el-footer {
  background-color: #B3C0D1;
  color: #333;
  text-align: center;
  line-height: 60px;
}

.el-aside {
  background-color: #E5E8ED;
  color: #333;
  text-align: center;
  /* line-height: 800px; */
}

.el-main {
  background-color: #E9EEF3;
  color: #333;
  text-align: center;
}

body>.el-container {
  margin-bottom: 40px;
}
</style>
