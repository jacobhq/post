<template>
  <div class="center">
    <h1>
      <code>/Post</code>
    </h1>
    <p>Weekly tech news to your inbox</p>
    <v-btn depressed color="primary" @click="sub" :loading="loading" :disabled="loading">Sign me up</v-btn>
    <v-btn text color="primary" to="/archive">Go to archive</v-btn>
  </div>
</template>

<script>
export default {
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
