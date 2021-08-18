<template>
  <div>
    <li v-for="post of posts" :key="post.slug">
      <NuxtLink :to="post.slug">{{ post.title }}</NuxtLink>
    </li>
  </div>
</template>

<script>
export default {
   async asyncData({ $content }) {
    const posts = await $content("blog").fetch();

    return {
      posts,
    };
  },
};
</script>

<style>
li{
  list-style: none;
  background-color: black;
  float: left;
  margin: 200px;
  padding: 200px;
}
</style>
