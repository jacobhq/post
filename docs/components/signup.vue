<template>
  <!-- Begin Mailchimp Signup Form -->
<div id="mc_embed_signup">
<v-form action="https://anchor.us17.list-manage.com/subscribe/post?u=22c14fa2c4ccc79555a27ecd1&amp;id=addfa88c25" method="post" id="mc-embedded-subscribe-form" name="mc-embedded-subscribe-form" class="validate" target="_blank">
	  <h1>Subscribe</h1>
    <small class="grey--text text--darken-1" style="margin-top: 5px">None of this data is shared with anyone.</small>
    <v-text-field label="Email Address" name="EMAIL" v-model="email" :rules="emailRules" required></v-text-field>
    <v-text-field label="First name" name="FNAME" v-model="firstname" :rules="nameRules" :counter="10" required></v-text-field>
    <v-text-field label="Last name" name="LNAME" v-model="lastname" :rules="nameRules" :counter="10"></v-text-field>
    <div style="position: absolute; left: -5000px;" aria-hidden="true"><input type="text" name="b_22c14fa2c4ccc79555a27ecd1_addfa88c25" tabindex="-1" value=""></div>
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
    firstname: '',
    lastname: '',
    nameRules: [
      v => !!v || 'Name is required',
      v => v.length <= 10 || 'Name must be less than 10 characters',
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
