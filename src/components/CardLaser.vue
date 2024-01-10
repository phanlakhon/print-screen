<template>
  <div v-for="post in   posts  " :key="post.title" class="loader" :style="'--clr:' + post.color + '; --i:0'">
    <h1>{{ post.title }}</h1>
  </div>
</template>

<script lang='ts'>
export default {
  data() {
    return {
      posts: [
        { title: 'hello', color: '#01e100' },
        { title: '123', color: '#f50076' },
        { title: 'hello', color: '#00e6fd' }
      ]
    };
  },
  created() {

  }
};
</script>