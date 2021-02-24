<template>
<div>
  <v-dialog
      v-model="dialog"
      width="500"
    >
      <template v-slot:activator="{ on, attrs }" style="padding-top: 10px;">
        <div style="margin-top: 10px;">
          <v-btn depressed color="primary" v-bind="attrs" v-on="on">Share us</v-btn>
          <v-btn text color="primary" @click="sub" :loading="loading" :disabled="loading">Go home</v-btn>
        </div>
      </template>

      <v-card>
        <v-card-title class="headline">
          Share us
        </v-card-title>

        <v-divider></v-divider>

        <v-card-text>
          <div class="row" style="padding-left: 15px; padding-bottom: 5px; margin-top: 15px;">
            <v-btn color="primary" depressed fab>
              <v-icon>mdi-email</v-icon>
            </v-btn>
            <v-btn color="primary" depressed fab style="margin-left: 10px;" href="https://twitter.com/compose/tweet?text=I%20just%20subscribed%20to%20Post%2C%20an%20awesome%20newsletter%20by%20%40jacobhq.%20Check%20it%20out%20at%20post-news.vercel.app!" target="_blank">
              <v-icon>mdi-twitter</v-icon>
            </v-btn>
            <v-btn color="primary" depressed fab style="margin-left: 10px;">
              <v-icon>mdi-facebook</v-icon>
            </v-btn>
          </div>
        </v-card-text>

        <v-divider></v-divider>

        <v-card-actions>
          <v-spacer></v-spacer>
          <v-btn
            color="primary"
            text
            @click="dialog = false"
          >
            Close
          </v-btn>
        </v-card-actions>
      </v-card>
  </v-dialog>
  <v-dialog
      v-model="emailDialog"
      width="500"
    >
      <template v-slot:activator="{ on, attrs }" style="padding-top: 10px;">
        <div style="margin-top: 10px;">
          <v-btn depressed color="primary" v-bind="attrs" v-on="on">Share us</v-btn>
          <v-btn text color="primary" @click="sub" :loading="loading" :disabled="loading">Go home</v-btn>
        </div>
      </template>

      <v-card>
        <v-card-title class="headline">
          Share us
        </v-card-title>

        <v-divider></v-divider>

        <v-card-text>
          <div class="row" style="padding-left: 15px; padding-bottom: 5px; margin-top: 15px;">
            <v-btn color="primary" depressed fab>
              <v-icon>mdi-email</v-icon>
            </v-btn>
            <v-btn color="primary" depressed fab style="margin-left: 10px;" href="https://twitter.com/compose/tweet?text=I%20just%20subscribed%20to%20Post%2C%20an%20awesome%20newsletter%20by%20%40jacobhq.%20Check%20it%20out%20at%20post-news.vercel.app!" target="_blank">
              <v-icon>mdi-twitter</v-icon>
            </v-btn>
            <v-btn color="primary" depressed fab style="margin-left: 10px;">
              <v-icon>mdi-facebook</v-icon>
            </v-btn>
          </div>
        </v-card-text>

        <v-divider></v-divider>

        <v-card-actions>
          <v-spacer></v-spacer>
          <v-btn
            color="primary"
            text
            @click="dialog = false"
          >
            Close
          </v-btn>
        </v-card-actions>
      </v-card>
  </v-dialog>
  </div>
</template>

<script>
export default {
  data() {
    return {
      emailDialog: false
    }
  }
}
</script>

<style>

</style>
