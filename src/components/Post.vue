<template lang="pug">
  li
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
