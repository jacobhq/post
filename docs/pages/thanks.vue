<template>
  <div class="center">
    <h1>Thank you for subscribing</h1>
    <small class="grey--text text--darken-1" style="margin-top: 5px">You will now recieve an email from us every week.</small>
    <br />
    <v-dialog v-model="dialog" width="500">
      <template v-slot:activator="{ on, attrs }" style="padding-top: 10px">
        <div style="margin-top: 10px">
          <v-btn depressed color="primary" v-bind="attrs" v-on="on"
            >Share us</v-btn
          >
          <v-btn
            text
            color="primary"
            @click="sub"
            :loading="loading"
            :disabled="loading"
            >Go home</v-btn
          >
        </div>
      </template>

      <v-card>
        <v-card-title class="headline"> Share us </v-card-title>

        <v-divider></v-divider>

        <v-card-text>
          <v-dialog v-model="emailDialog" width="500">
      <template v-slot:activator="{ on, attrs }" style="padding-top: 10px">
        <div
            class="row"
            style="padding-left: 15px; padding-bottom: 5px; margin-top: 15px"
          >
            <v-btn color="primary" depressed fab disabled v-bind="attrs" v-on="on">
              <v-icon>mdi-email</v-icon>
            </v-btn>
            <v-btn
              color="primary"
              depressed
              fab
              style="margin-left: 10px"
              href="https://twitter.com/compose/tweet?text=I%20just%20subscribed%20to%20Post%2C%20an%20awesome%20newsletter%20by%20%40jacobhq.%20Check%20it%20out%20at%20post-news.vercel.app!"
              target="_blank"
            >
              <v-icon>mdi-twitter</v-icon>
            </v-btn>
            <v-btn color="primary" depressed fab style="margin-left: 10px">
              <v-icon>mdi-facebook</v-icon>
            </v-btn>
          </div>
      </template>

      <v-card>
        <v-card-title class="headline">Email a friend</v-card-title>
        <v-card-text><small class="grey--text text--darken-1">Your default email application will be used to send the email.</small></v-card-text>
        <v-divider></v-divider>

        <v-card-text>
          <div class="col" style="padding-left: 15px; padding-bottom: 5px; margin-top: 15px">
              <v-text-field label="Your friend's email" type="email" v-model="email" />
              <v-text-field label="Email subject" type="text" v-model="subject" v-on:change="encode()" />
              <v-textarea label="Message" v-model="message" v-on:change="encode()" />
          </div>
        </v-card-text>

        <v-divider></v-divider>

        <v-card-actions>
          <v-spacer></v-spacer>
          <v-form :action="mailto">
              <v-text-field label="Email" depressed type="email" v-model="email" style="display: none;" />
              <v-text-field label="Email subject" type="text" v-model="encodedSubject" style="display: none;" />
              <v-textarea label="Message" v-model="encodedMessage" style="display: none;" />
              <v-btn color="primary" text @click="emailDialog = false"> Close </v-btn>
              <v-btn color="primary" type="submit"> Send </v-btn>
          </v-form>
        </v-card-actions>
      </v-card>
    </v-dialog>
        </v-card-text>

        <v-divider></v-divider>

        <v-card-actions>
          <v-spacer></v-spacer>
          <v-btn color="primary" text @click="dialog = false"> Close </v-btn>
        </v-card-actions>
      </v-card>
    </v-dialog>
  </div>
</template>

<script>
import Signup from "../components/signup.vue";
import Share from "../components/share.vue";

export default {
  components: {
    Signup,
    Share,
  },
  data() {
    return {
      loader: null,
      loading: false,
      dialog: false,
      emailDialog: false,
      email: '',
      subject: '',
      encodedSubject: '',
      message: 'I just subscribed to Post, an awesome newsletter by @jacobhq. Check it out at post-news.vercel.app!',
      encodedMessage: '',
      mailto: ''
    };
  },
  methods: {
    sub() {
      this.loader = "loading";
      setTimeout(() => {
        this.$router.push({ path: "/" });
      }, 1000);
    },
    encode() {
        this.encodedSubject = encodeURIComponent(this.subject);
        this.encodedMessage = encodeURIComponent(this.message);
        this.mailto = 'mailto:' + this.email + '?' + 'subject=' + this.encodedSubject + '&body=' + this.encodedMessage;
    }
  },
  watch: {
    loader() {
      const l = this.loader;
      this[l] = !this[l];

      setTimeout(() => (this[l] = false), 3000);

      this.loader = null;
    },
  },
};
</script>

<style></style>
