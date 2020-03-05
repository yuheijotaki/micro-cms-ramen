<template lang="pug">
  li
    nuxt-link(:to="`/posts/${post.id}/`")
      p.image
        img(:src="post.image.url")
      p.name {{ post.name }}
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

<style lang="scss" scoped>
li {
  width: 22.5%;
  margin-top: 3.3%;
  margin-right: 3.3%;
  &:nth-child(4n) {
    margin-right: 0;
  }
}
a {
  display: block;
  color: #111;
  text-decoration: none;
}
.image {
  font-size: 0;
  line-height: 0;
  border: #aaa 1px solid;
  img {
    width: 100%;
    height: auto;
  }
}
.name {
  margin-top: 10px;
  font-size: 16px;
  line-height: 1.4;
  font-weight: bold;
  text-align: center;
}
</style>
