<template>
  <!-- <div class="home"> -->
    <Post />
  <!-- </div> -->
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';
import Post from '@/components/Post.vue'; // @ is an alias to /src

@Component({
  components: {
    Post,
  },
})
export default class Home extends Vue {}
</script>
