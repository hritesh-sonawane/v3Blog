<template>
  <card 
    v-for="post in store.state.posts"
  >
  <template v-slot:title>
    {{ post.title }}
  </template>

  <template v-slot:content>
    {{ post.content }}
  </template>

  <template v-slot:description>
    <Controls :post="post" />
  </template>
  </card>
  {{ currentHashtag }}
</template>

<script>
import { store } from './store'
import Card from './Card.vue'
import Controls from './Controls.vue'
import { ref } from 'vue'

  export default {
    components: {
      Card,
      Controls
    },
    setup() {
      const currentHashtag = ref()
      const setHashtag = (tag) => {
        currentHashtag.value = tag
      }
      return {
        store,
        setHashtag, 
        currentHashtag
      }
    }
  }
</script>

<style scoped>

</style>