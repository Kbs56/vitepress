<script setup lang="ts">
import { data as posts } from "../data/latestPosts.data.ts";
</script>

<template>
  <h1>Most Recent Blog Posts</h1>
  <h2 v-if="!posts.length">None yet, but many to come...</h2>
  <div class="container">
    <ul class="list">
      <li class="post" v-for="post of posts" :key="post">
        <a class="title" :href="post.url">{{ post.frontmatter.title }}</a>
        <span>{{ post.frontmatter.description }}</span>
      </li>
    </ul>
  </div>
</template>
<style scoped>
h1 {
  color: var(--vp-c-white);
  opacity: 90%;
  padding-top: 20px;
}

h2 {
  color: #00d2ff;
  opacity: 90%;
}

a {
  font-size: 24px;
  text-decoration: none;
  color: #00d2ff;
  opacity: 90%;
}

a:hover {
  color: #c0c0c0;
}

.container {
  margin-top: 20px;
}

.list {
  list-style: none;
  padding: 0;
  margin: 0;
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 10px;
  row-gap: 30px;
  align-items: baseline;
}

.list li {
  border: 1px solid var(--vp-c-bg-soft);
  background-color: var(--vp-c-bg-soft);
  border-radius: 12px;
  padding: 20px;
  text-align: left;
  display: flex;
  flex-direction: column;
  height: 250px;
  grid-template-columns: subgrid;
}

.list span {
  margin-top: 14px;
  height: 100%;
  align-items: center;
  display: flex;
}

/* Media query for tablets and smaller devices */
@media (max-width: 768px) {
  .list {
    grid-template-columns: repeat(2, 1fr);
    /* 2 columns on medium screens */
  }
}

/* Media query for mobile phones */
@media (max-width: 480px) {
  .list {
    grid-template-columns: 1fr;
    /* 1 column on small screens */
  }
}
</style>
