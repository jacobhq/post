<template>
  <div>
    <div class="center">
    <h1>
      <code>/archive</code>
    </h1>
    <p>Welcome to the post archive</p>
    <v-btn depressed color="primary" @click="sub" :loading="loading" :disabled="loading">Signup</v-btn>
    <v-btn text color="primary" href="#feed">Get reading</v-btn>
  </div>
  <v-container style="margin-top: 85vh; margin-bottom: 50px;" id="feed">
    <v-card outlined>
      <v-card-title>Welcome</v-card-title>
      <v-card-text>Welcome to this newsletter</v-card-text>
      <v-card-actions>
        <v-btn text color="primary">Read</v-btn>
      </v-card-actions>
    </v-card>
  </v-container>
  </div>
</template>

<script>
export default {
  layout: 'feed',
  head: {
    title: 'Feed'
  },
  data() {
    return {
      loader: null,
      loading: false
    }
  },
  methods: {
    sub() {
      this.loader = 'loading'
      setTimeout(() => {  this.$router.push({path: '/signup'}) }, 1000)
    }
  },
  created() {
    this.$router.go('/')
  },
  watch: {
      loader () {
        const l = this.loader
        this[l] = !this[l]

        setTimeout(() => (this[l] = false), 3000)

        this.loader = null
      },
    }
}
</script>
