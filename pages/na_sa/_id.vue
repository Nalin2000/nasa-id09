<template>
  <div>
    <h1>{{ date }}</h1>
    <v-card
      class="mx-auto mb-7 mt-3 a"
      color="rgba(1,4,56)"
      dark
      max-width="800"
    >
      <v-card-title>
        <v-icon color="white" large left> mdi-rocket </v-icon>
        <span class="title font-weight-bold">Explanation</span>
      </v-card-title>

      <v-card-text class="headline font-weight-medium">
        " {{ ex }} "
      </v-card-text>

      <v-card-actions>
        <v-list-item class="grow">
          <v-list-item-avatar color="black darken-3">
            <v-img
              class="elevation-6"
              alt=""
              src="https://www.nasa.gov/sites/default/files/thumbnails/image/nasa-logo-web-rgb.jpg"
            ></v-img>
          </v-list-item-avatar>

          <v-list-item-content>
            <v-list-item-title>Nasa</v-list-item-title>
          </v-list-item-content>

          <v-row align="center" justify="end">
            <v-dialog
              v-model="dialog"
              fullscreen
              hide-overlay
              transition="dialog-bottom-transition"
            >
              <template v-slot:activator="{ on, attrs }">
                <v-btn color="dark" class="mr-2" dark v-bind="attrs" v-on="on">
                  See Picture
                </v-btn>
              </template>
              <v-card>
                <v-toolbar dark color="primary">
                  <v-btn icon dark @click="dialog = false">
                    <v-icon>mdi-close</v-icon>
                  </v-btn>
                  <v-toolbar-title>{{ title }}</v-toolbar-title>

                  <v-spacer></v-spacer>
                </v-toolbar>
                <v-img :src="url" height="auto" max-height="680"></v-img>
              </v-card>
            </v-dialog>

            <v-btn color="dark" nuxt to="/na_sa"> Back </v-btn>
          </v-row>
        </v-list-item>
      </v-card-actions>
    </v-card>
  </div>
</template>
<script>
export default {
  data() {
    return {
      dialog: false,
      notifications: false,
      sound: true,
      widgets: false,
      ex: this.$route.params.id.explanation,
      date: this.$route.params.id.date,
      title: this.$route.params.id.title,
      url: this.$route.params.id.url,
    }
  },
}
</script>
<style>
.a {
  color: #000;
}
</style>
