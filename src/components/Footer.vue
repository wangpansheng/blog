<template>
  <el-footer>
    <!-- Power by wwww -->
    {{msg}}
  </el-footer>
</template>

<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator';

@Component
export default class Footer extends Vue {
  // @Prop() private msg!: string;
  public msg: string = 'Power by wwww';
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.el-footer {
  // height: 100px;
  // line-height: 100px;
  // background: rgba($color: #000000, $alpha: 0.8);
  // color: rgba($color: #ffffff, $alpha: 1);
  background-color: #b3c0d1;
  color: #333;
  text-align: center;
  line-height: 60px;
}
</style>
