<template>
  <v-btn icon href="https://github.com/jacobhq/post" target="_blank" @click="star()">
    <v-icon v-show="!starred">mdi-star</v-icon>
    <v-icon v-show="starred" color="orange">mdi-star</v-icon>
  </v-btn>
</template>

<script>
export default {
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

</style>
