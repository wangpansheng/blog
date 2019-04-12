<template>
  <div id="app">
    <!-- <el-container> -->
    <Header/>
    <el-main>
      <router-view/>
    </el-main>
    <Footer/>
    <!-- </el-container> -->
  </div>
</template>

<script lang="ts">
import { Component, Prop, Vue } from "vue-property-decorator";
import Header from "@/components/Header.vue";
// import Header from '@/components/Nav.vue';
import Footer from "@/components/Footer.vue";

@Component({
  components: {
    Header,
    Footer
  }
})
export default class App extends Vue {
  // @Prop() private msg!: string;
}
</script>
<style lang="scss">
* {
  // font-family: "Quattrocento Sans", -apple-system, BlinkMacSystemFont,
  //   "avenir next", avenir, "helvetica neue", helvetica, ubuntu, roboto, noto,
  //   "segoe ui", arial, sans-serif;
  font-family: Avenir, Helvetica, Arial, sans-serif;
  margin: 0;
  padding: 0;
  text-decoration: none;
}
#app {
  // font-family: "Avenir", Helvetica, Arial, sans-serif;
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  min-height: 100vh;
  display: flex;
  flex-flow: column nowrap;
  justify-content: space-between;
}
// body > .el-container {
//   height: 100%;
//   margin-bottom: 40px;
//   display: flex;
//   flex-flow: column nowrap;
//   justify-content: space-between;
// }
.el-main {
  // background-color: #e9eef3;
  background: #fff;
  color: #333;
  text-align: center;
  // line-height: 160px;
}
</style>
