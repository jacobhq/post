<template>
    <v-footer
      padless
      absolute
    >
      <v-card
        flat
        tile
        width="100%"
        class="red lighten-1 text-center"
      >
        <v-card-text>
        </v-card-text>

        <v-divider></v-divider>

        <v-card-text class="white--text">
          {{ new Date().getFullYear() }} - <strong>Jacob Marshall</strong>
        </v-card-text>
      </v-card>
    </v-footer>
</template>
