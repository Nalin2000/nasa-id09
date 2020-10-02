<template>
  <v-parallax
    src="https://i.pinimg.com/originals/31/b8/58/31b8582debf918f7573f47779a95651a.gif"
    height="auto"
    jumbotron
  >
    <v-row justify="center" align="center">
      <v-col cols="12" sm="8" md="6">
        <div align="center">
          <vuetify-logo />
        </div>
        <v-card class="mt-5" color="rgba(0,0,0,0.8)">
          <v-card-title class="headline"> Welcome to the space </v-card-title>
          <v-card-text>
            <p>
              This is Astronomy Picture of the Day from NASA. If you need to see
              the best picture please click to continue!!
            </p>

            <p>Thank you for visiting our Web site.</p>
            <div class="text-xs-right">
              <em><small>&mdash; Nalin S.</small></em>
            </div>
            <hr class="my-3" />
            <br />
            <h3>
              <a
                href="https://github.com/Nalin2000/nasa-id09.git"
                target="_blank"
                rel="noopener noreferrer"
              >
                GitHub
              </a>
            </h3>
          </v-card-text>
          <v-card-actions>
            <v-spacer />
            <v-btn color="info" nuxt to="/na_sa"> Continue </v-btn>
          </v-card-actions>
        </v-card>
      </v-col>
    </v-row>
  </v-parallax>
</template>

<script>
import VuetifyLogo from '~/components/VuetifyLogo.vue'

export default {
  components: {
    VuetifyLogo,
  },
}
</script>
