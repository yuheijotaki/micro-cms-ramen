<template lang="pug">
  div
    Logo
    section
      h1.name {{ post.name }}
      div(
        v-html="post.content"
      )
    section
      h2.heading カテゴリー
      ul.category
        li(v-for="item in post.category") {{item.category}}
    section
      h2.heading 食べログURL
      p.url
        a(:href="post.url" target="_blank") {{ post.url }}
    section
      p.image
        img(:src="post.image.url")
    section
      p
        nuxt-link(to="/") トップへ戻る
</template>

<script>
import Logo from '~/components/Logo.vue'
import axios from 'axios'

export default {
  components: {
    Logo
  },
  async asyncData( { params } ) {
    const { data } = await axios.get(
      `${process.env.API_URL}/${params.id}`,
      {
        headers: { 'X-API-KEY': process.env.API_KEY }
      }
    )
    return {
      post: data
    }
  }
};
</script>

<style lang="scss" scoped>
div {
  max-width: 600px;
  margin-top: 40px;
}
section {
  margin-top: 40px;
}
h1 {
  color: #111;
  font-size: 30px;
}
h2 {
  color: #111;
  font-size: 18px;
}
.category {
  display: flex;
  padding-left: 1em;
  li {
    margin-right: 40px;
  }
}
.image {
  font-size: 0;
  line-height: 0;
  img {
    width: 100%;
    height: auto;
  }
}
</style>
