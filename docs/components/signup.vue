<template>
  <!-- Begin Mailchimp Signup Form -->
<div id="mc_embed_signup">
<v-form action="https://mail.jacobhq.xyz/subscription/form" method="post" id="mc-embedded-subscribe-form" name="mc-embedded-subscribe-form" target="_blank">
	  <h1>Subscribe</h1>
    <small class="grey--text text--darken-1" style="margin-top: 5px">None of this data is shared with anyone, and it is only used to send you email.</small>
    <br>
    <v-text-field label="Email Address *" name="email" v-model="email" :rules="emailRules" required></v-text-field>
    <v-text-field label="First name *" name="name" v-model="firstname" :rules="nameRules" :counter="25" required></v-text-field>
    <input id="8d933" type="checkbox" name="l" value="8d9335ad-cdba-4018-9fd8-4e08e07485ac" v-model="post" style="display: none;" />
    <div style="margin-top: 10px;">
      <v-btn depressed color="primary" type="submit" value="Subscribe" name="subscribe">Signup</v-btn>
      <v-btn text color="primary" @click="sub" :loading="loading" :disabled="loading">Go home</v-btn>
    </div>
</v-form>
</div>

<!--End mc_embed_signup-->
</template>

<script>
export default {
  head: {
    title: 'Signup'
  },
  data() {
    return {
      loader: null,
      loading: false,
      valid: false,
      post: true,
    firstname: '',
    lastname: '',
    nameRules: [
      v => !!v || 'Name is required',
      v => v.length <= 25 || 'Name must be less than 25 characters',
    ],
    email: '',
    emailRules: [
      v => !!v || 'E-mail is required',
      v => /.+@.+/.test(v) || 'E-mail must be valid',
    ],
    }
  },
  methods: {
    sub() {
      this.loader = 'loading'
      setTimeout(() => {  this.$router.push({path: '/'}) }, 1000)
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
