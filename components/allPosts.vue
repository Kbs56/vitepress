<script setup lang="ts">
import { data as posts } from "../data/allPosts.data.ts";
console.log(posts);

function convertDate(dateString) {
  const date = new Date(dateString);
  const formattedDate = date.toLocaleDateString("en-US", {
    year: "numeric",
    month: "long",
    day: "numeric",
  });
  return formattedDate;
}
</script>

<template>
  <div class="container">
    <ul>
      <li v-for="post of posts">
        <a :href="post.url">{{ post.frontmatter.title }}</a>
        <span>{{ post.frontmatter.author }} |
          {{ convertDate(post.frontmatter.date) }}</span>
        <p>{{ post.frontmatter.description }}</p>
      </li>
    </ul>
  </div>
</template>

<style scoped>
ul {
  list-style: none;
  display: flex;
  flex-direction: column;
  gap: 20px;
}

a {
  font-size: 24px;
  text-decoration: none;
  color: #00d2ff;
  line-height: 30px;
}

a:hover {
  color: #c0c0c0;
}

li {
  display: flex;
  flex-direction: column;
  border: 1px solid var(--vp-c-bg-soft);
  background-color: var(--vp-c-bg-soft);
  border-radius: 12px;
  height: 100%;
  padding-left: 10px;
  padding-right: 10px;
  padding-top: 15px;
}

span {
  color: #ebebf599;
  opacity: 80%;
  padding-top: 8px;
}
</style>
