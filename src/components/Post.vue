<template lang="pug">
  li
    nuxt-link(:to="`/posts/${post.id}/`")
      p id: {{ post.id }}
      p title: {{ post.title }}
</template>

<script>
export default {
  name: 'Post',
  props:{
    'post': {
      type: Object,
      default: ''
    }
  }
}
</script>
