<template>
<div>
  <v-card class="overflow-hidden">
    <v-app-bar
      absolute
      color="white"
      elevate-on-scroll
      scroll-target="#scrolling-techniques-7"
    >

      <v-toolbar-title>
        <code>/Post</code>
      </v-toolbar-title>

      <v-spacer></v-spacer>

      <v-btn icon href="https://github.com/jacobhq/post" target="_blank">
        <v-icon color="orange">mdi-star</v-icon>
      </v-btn>
    </v-app-bar>
    <v-sheet
      id="scrolling-techniques-7"
      class="overflow-y-auto"
      max-height="600"
    >
      <v-container>
        <Nuxt />
      </v-container>
    </v-sheet>
  </v-card>
  <pagefooter />
</div>
</template>

<script>
import pagefooter from '../components/footer'

export default {
  components: {
    pagefooter
  },
  data () {
    return {
      clipped: false,
      drawer: false,
      fixed: false,
      items: [
        {
          icon: 'mdi-apps',
          title: 'Welcome',
          to: '/'
        },
        {
          icon: 'mdi-chart-bubble',
          title: 'Inspire',
          to: '/inspire'
        }
      ],
      miniVariant: false,
      right: true,
      rightDrawer: false,
      title: 'Vuetify.js'
    }
  }
}
</script>

<style>
* {
  font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
}
</style>
