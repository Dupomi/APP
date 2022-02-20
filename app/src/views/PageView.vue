<template>
    Page id is {{$route.params.pageId}}
    {{ info }}
    <router-link :to='`/page/${$route.params.pageID}/comments`'>Page's Comments</router-link>
    <router-view></router-view>
</template>
<script>
import axios from 'axios'

export default {
  data () {
    return {
      info: null
    }
  },
  mounted () {
    axios
      .get('https://jsonplaceholder.typicode.com/todos/1')
      .then(response => (this.info = response.data))
  }
}
</script>
