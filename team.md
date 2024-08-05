---
layout: page
---

<script setup>
import {
  VPTeamPage,
  VPTeamPageTitle,
  VPTeamMembers
} from 'vitepress/theme'

const members = [
  {
    avatar: 'https://github.com/ianhockett.png',
    name: 'Ian Hockett',
    title: 'Engineering Manager',
    links: [
      { icon: 'github', link: 'https://github.com/ianhockett' },
      { icon: 'twitter', link: 'https://x.com/ian_hockett' }
    ]
  },
  {
    avatar: 'https://www.github.com/Kbs56.png',
    name: 'Kenny Sheldon',
    title: 'Platform Engineer',
    links: [
      { icon: 'github', link: 'https://github.com/Kbs56' },
      { icon: 'twitter', link: 'https://twitter.com/kbs_56' }
    ]
  },
]
</script>

<VPTeamPage>
  <VPTeamPageTitle>
    <template #title>
      Our Team
    </template>
    <template #lead>
      The development of this product is guided by an international
      team, some of whom have chosen to be featured below.
    </template>
  </VPTeamPageTitle>
  <VPTeamMembers
    :members="members"
  />
</VPTeamPage>
