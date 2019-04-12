<template>
  <div class="post">
    <div class="item-post" v-for="item in list" v-bind:key="item.id">
      <div class="left">
        <h4 class="title">{{item.title}}</h4>
        <p class="subtit">{{item.desc}}</p>
        <div class="meta">{{item.date}}</div>
      </div>
      <div class="img" v-if="item.img">
        <img :src="item.img" :alt="item.title">
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { Component, Prop, Vue } from "vue-property-decorator";

@Component
export default class HelloWorld extends Vue {
  // @Prop() private msg!: string;
  private list: Array<object> = [
    {
      title: "这是一个文章",
      desc:
        "这是一个文章这是一个文章这是一个文章这是一个文章这是一个文章这是一个文这是一个文章这是一个文章这是一个文章这是一个文章这是一个文章这是一个文章这是一个文章这是一个文章这是一个文章这是一个文章章",
      img: "99",
      date: "2018-09-08",
      id: "9"
    },
    {
      title: "这是一个文章",
      desc:
        "这是一个文章这是一个文章这是一个文章这是一个文章这是一个文章这是一个文这是一个文章这是一个文章这是一个文章这是一个文章这是一个文章这是一个文章这是一个文章这是一个文章这是一个文章这是一个文章章",
      img: "",
      date: "2018-09-08",
      id: "9"
    },
    {
      title: "这是一个文章",
      desc:
        "这是一个文章这是一个文章这是一个文章这是一个文章这是一个文章这是一个文这是一个文章这是一个文章这是一个文章这是一个文章这是一个文章这是一个文章这是一个文章这是一个文章这是一个文章这是一个文章章",
      img: "",
      date: "2018-09-08",
      id: "9"
    },
    {
      title: "这是一个文章",
      desc:
        "这是一个文章这是一个文章这是一个文章这是一个文章这是一个文章这是一个文这是一个文章这是一个文章这是一个文章这是一个文章这是一个文章这是一个文章这是一个文章这是一个文章这是一个文章这是一个文章章",
      img: "",
      date: "2018-09-08",
      id: "9"
    },
    {
      title: "这是一个文章",
      desc:
        "这是一个文章这是一个文章这是一个文章这是一个文章这是一个文章这是一个文这是一个文章这是一个文章这是一个文章这是一个文章这是一个文章这是一个文章这是一个文章这是一个文章这是一个文章这是一个文章章",
      img: "",
      date: "2018-09-08",
      id: "9"
    },
    {
      title: "这是一个文章",
      desc:
        "这是一个文章这是一个文章这是一个文章这是一个文章这是一个文章这是一个文这是一个文章这是一个文章这是一个文章这是一个文章这是一个文章这是一个文章这是一个文章这是一个文章这是一个文章这是一个文章章",
      img: "",
      date: "2018-09-08",
      id: "9"
    },
    {
      title: "这是一个文章",
      desc:
        "这是一个文章这是一个文章这是一个文章这是一个文章这是一个文章这是一个文这是一个文章这是一个文章这是一个文章这是一个文章这是一个文章这是一个文章这是一个文章这是一个文章这是一个文章这是一个文章章",
      img: "",
      date: "2018-09-08",
      id: "9"
    },
    {
      title: "这是一个文章",
      desc:
        "这是一个文章这是一个文章这是一个文章这是一个文章这是一个文章这是一个文这是一个文章这是一个文章这是一个文章这是一个文章这是一个文章这是一个文章这是一个文章这是一个文章这是一个文章这是一个文章章",
      img: "",
      date: "2018-09-08",
      id: "9"
    }
  ];
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.post {
  padding: 0 100px;
  .item-post {
    display: flex;
    flex-flow: row;
    justify-content: space-around;
    align-items: center;
    padding: 20px;
    background: #fff;
    border-bottom: 1px solid rgba(0, 0, 0, 0.1);
    // border-radius: 5px;
    // margin-bottom: 20px;
    height: 100px;
    overflow: hidden;
    text-align: left;
    .title {
      color: #333;
      margin: 7px 0 4px;
      display: inherit;
      font-size: 18px;
      font-weight: 700;
      line-height: 1.5;
    }
    .subtit {
      min-height: 30px;
      margin: 0 0 8px;
      font-size: 13px;
      line-height: 24px;
      color: #555;
    }
    .meta {
      padding-right: 0 !important;
      font-size: 12px;
      font-weight: 400;
      line-height: 20px;
    }
    .img {
      margin-left: 10px;
      border-radius: 6px;
      overflow: hidden;
      background-color: rgba(0, 0, 0, 0.1);
      width: 300px;
      height: 100px;
    }
  }
}
</style>
