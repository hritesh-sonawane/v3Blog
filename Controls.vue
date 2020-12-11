<template>
  <div>
    <button>
      {{ post.likes }}
    </button>
    <Hashtag 
      v-for="tag in post.hashtags" 
      :hashtag="tag"
      @setHashtag="setHashtag"
    />
  </div>
</template>

<script>
import Hashtag from './Hashtag.vue'

export default {
  components: {
    Hashtag
  },

  props: {
    post: {
      type: Object
    }
  },

  setup(props, ctx) {
    const setHashtag =(tag) => {
      console.log(tag);
      ctx.emit('setHashtag', props.hashtag)
    }
    return {
      setHashtag
    }
  }
}
</script>

<style scoped>

</style>