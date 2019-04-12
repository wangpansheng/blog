<template>
  <el-header class="header">
    <!-- <div class="header"> -->
    <!-- <div class="bg"> -->
    <!-- <nav>
      <div>
        <router-link to="/">
          <img class="avatar" src="https://story.xaprb.com/img/logo.jpg" alt="avatar">
        </router-link>
      </div>
      <div>
        <router-link class="nav-item" to="/">item</router-link>
        <router-link class="nav-item" to="/">item</router-link>
        <router-link class="nav-item" to="/">item</router-link>
        <router-link class="nav-item" to="/">item</router-link>
      </div>
    </nav>-->
    <!-- <div class="title">This is Header</div> -->
    <router-link to="/" class="avatar">
      <img src="https://story.xaprb.com/img/logo.jpg" alt="avatar">
    </router-link>
    <el-menu :default-active="activeIndex" mode="horizontal" @select="handleSelect">
      <el-menu-item v-for="(item) in list" v-bind:key="item.path" :index="item.path">
        <router-link :to="item.path" class="avatar">{{item.name}}</router-link>
      </el-menu-item>
    </el-menu>
    <!-- </div> -->
  </el-header>
  <!-- </div> -->
</template>

<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator';

@Component
export default class Header extends Vue {
  public activeIndex: string = '/';
  public list: object[] = [
    {
      index: 1,
      path: '/',
      name: '首页',
    },
    {
      index: 2,
      path: '/99',
      name: '文章',
    },
    {
      index: 2,
      path: '/999',
      name: '消息中心',
    },
  ];
  @Prop() private msg!: string;
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.header {
  width: 100%;
  // padding: 20px;
  margin: 0 auto;
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: center;
  // height: 200px;
  // background-image: url(https://story.xaprb.com/img/default-header-img.jpg);
  background-repeat: no-repeat;
  background-size: cover;
  background-position: center;
  font-size: 20px;
  color: #42b983;
  border-bottom: 1px solid rgba(0, 0, 0, 0.1);
  // .bg {
  //   background-color: rgba(0, 0, 0, 0.3);
  // }
  nav {
    width: 85%;
    margin: 0 auto;
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    padding: 0 20px;
    .nav-item {
      font-size: 18px;
      // color: #ffffff;
      color: rgba(0, 0, 0, 0.8);
      text-decoration: none;
      margin-left: 10px;
    }
  }
  .avatar {
    width: 30px;
    height: 30px;
    & > img {
      border-radius: 50%;
      width: 100%;
      height: 100%;
    }
  }
  // .title {
  //   padding: 100px;
  //   font-size: 30px;
  //   font-family: 'Quattrocento Sans', -apple-system, BlinkMacSystemFont, 'avenir next', avenir, 'helvetica neue', helvetica, ubuntu, roboto, noto, 'segoe ui', arial, sans-serif;
  //   color: #ffffff;
  // }
}
// h3 {
//   margin: 40px 0 0;
// }
// ul {
//   list-style-type: none;
//   padding: 0;
// }
// li {
//   display: inline-block;
//   margin: 0 10px;
// }
// a {
//   color: #42b983;
// }
</style>
