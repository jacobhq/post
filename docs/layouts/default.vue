<template>
<v-app>
  <v-card class="overflow-hidden" style="height: 100vh;">
    <v-app-bar
      absolute
      color="white"
      elevate-on-scroll
      scroll-target="#scrolling-techniques-7"
    >

      <v-toolbar-title>
        <nuxt-link to="/">
          <code>/Post</code>
        </nuxt-link>
      </v-toolbar-title>

      <v-spacer></v-spacer>

      <star />
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
</v-app>
</template>

<script>
import pagefooter from '../components/footer'
import Star from '../components/star.vue'

export default {
  components: {
    pagefooter,
    Star
  }
}
</script>

<style>
* {
  font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
}

.center {
  position: absolute;
    top: 50%;
    left: 50%;
    margin-right: -50%;
    transform: translate(-50%, -50%);
}

#no-shadow::before {
  box-shadow: none;
}

.v-expansion-panel-header {
  padding-left: 0;
}
</style>
