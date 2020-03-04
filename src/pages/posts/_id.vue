<template lang="pug">
  div
    p id: {{ post.id }}
    p title: {{ post.title }}
    div(
      v-html="post.content"
    )
</template>

<script>
import axios from 'axios'

export default {
  async asyncData( { params } ) {
    const { data } = await axios.get(
      `${process.env.API_URL}/${params.id}`,
      {
        headers: { "X-API-KEY": process.env.API_KEY }
      }
    )
    return {
      post: data
    }
  }
};
</script>
