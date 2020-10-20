<template>
  <v-row justify="center" align="center">
    <v-col cols="12" sm="8" md="6">
      <div class="text-center">
        <h1>Welcome</h1>
        <h1>{{ apiText }}</h1>
      </div>
    </v-col>
  </v-row>
</template>
<script>
import axios from 'axios'

export default {
  async asyncData () {
    const apiText = await axios.get('https://friendly-yalow-4a2e2c.netlify.app/.netlify/functions/hello')
      .then(res => res.data)
      .catch(err => JSON.stringify(err))
    return { apiText }
  },
  data () {
    return {
      title: 'NuxtSpaServer'
    }
  }
}
</script>
