---
# https://vitepress.dev/reference/default-theme-home-page
layout: home

hero:
  name: "My Awesome Project"
  text: "A VitePress Site"
  tagline: My great project tagline
  actions:
    - theme: brand
      text: Learn about tectonic
      link: /about
    - theme: alt
      text: Meet the team
      link: /team
---

<script setup lang='ts'>
  import homePosts from './components/homePosts.vue'
</script>

<homePosts />
