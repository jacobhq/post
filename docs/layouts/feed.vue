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

      <v-btn icon href="https://github.com/jacobhq/post" target="_blank" @click="star()">
        <v-icon v-show="!starred">mdi-star</v-icon>
        <v-icon v-show="starred" color="orange">mdi-star</v-icon>
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
</v-app>
</template>

<script>
import pagefooter from '../components/footer'

export default {
  components: {
    pagefooter
  },
  data () {
    return {
      starred: false
    }
  },
  methods: {
    star() {
      this.starred = true
    }
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
