<template>
  <ul>
    <li v-for="content in contents" :key="content.id">
      <nuxt-link :to="`/${content.id}`">
        {{ content.title }}
      </nuxt-link>
    </li>
  </ul>
</template>

<script>
import axios from 'axios'
export default {
  async asyncData() {
    const { data } = await axios.get(
      'https://sawamura.microcms.io/api/v1/blog',
      {
        headers: { 'X-API-KEY': 'xxxxxxxxxxxxxxx' }
      }
    )
    return data
  }
}
</script>