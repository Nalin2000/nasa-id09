<template>
  <v-parallax
    src="https://wallpapercave.com/wp/wp2487379.jpg"
    height="1000"
    width="1980"
    jumbotron
  >
    <v-layout>
      <v-flex class="text-center mb-1">
        <img src="/rocket1.png" alt="Vuetify.js" width="300rem" />
        <v-container class="center"
          ><input type="date" class="datee" v-model="keyword" />
          <button class="button" @click="searchData()">
            Search
          </button></v-container
        >
      </v-flex>
    </v-layout>
    <v-container class="mb-3"
      ><v-card class="mx-auto" max-width="500" v-if="result">
        <v-img :src="result.url" height="auto"></v-img>

        <v-card-title> {{ result.title }} </v-card-title>

        <v-card-actions>
          <v-btn color="lighten-2" text
            ><nuxt-link :to="{ name: 'na_sa-id', params: { id: result } }">
              See more</nuxt-link
            ></v-btn
          >
        </v-card-actions>
      </v-card>
      <model v-if="error" @close="showModal = false">
        <h1 slot="body" class="bo">
          Date must be between Jun 16, 1995 and Today
        </h1>
        <h3 slot="footer">
          <button class="button-a mt-5" @click="reset()">Click to reset</button>
        </h3>
      </model></v-container
    >
  </v-parallax>
</template>
<script>
import axios from 'axios'
import model from '../../components/model'
export default {
  components: {
    model,
  },
  data() {
    return {
      result: {},
      keyword: '',
      error: false,
    }
  },
  methods: {
    searchData() {
      axios
        .get(
          'https://api.nasa.gov/planetary/apod?api_key=rWSo915pVNWHhs2nvnix2ow3sh3aABlw9mwYwJuv&date=' +
            this.keyword
        )
        .then((response) => {
          this.result = response.data
          console.log(this.result)
        })
        .catch((err) => {
          console.log('E: ' + err)
          this.error = true
        })
    },

    reset() {
      Object.assign(this.$data, this.$options.data())
    },
  },
}
</script>

<style>
.button {
  background-color: rgb(151, 228, 252);
  border: none;
  color: rgb(17, 0, 255);
  padding: 5px 5px 5px 5px;
  text-align: center;
  display: inline-block;
  margin: 10px 5px;
  font-size: 2rem;
  cursor: pointer;
  border-radius: 12px;
  border: 0.5px solid rgb(151, 228, 252);
  width: 10rem;
}

button:hover {
  color: rgb(222, 140, 255);
  border: 0.5px solid rgba(0, 0, 0, 0.664);
  background-color: rgba(0, 0, 0, 0.664);
}

.button-a {
  background-color: rgb(125, 177, 255);
  border: none;
  padding: 5px 5px 5px 5px;
  text-align: center;
  display: inline-block;
  margin: 10px 10px;
  font-size: 2vw;
  cursor: pointer;
  border-radius: 15px;
  border: 0.5px solid rgb(42, 5, 250);
  width: 15rem;
}
button-a:hover {
  color: rgb(207, 124, 255);
  border: 0.5px solid rgba(255, 255, 255, 0.664);
  background-color: rgba(3, 3, 3, 0.664);
}
.bo {
  color: white;
  font-size: 50px;
}

.datee {
  border-radius: 8px;
  padding: 12px;
  border: 2px solid #ffffff;
  font-size: 20px;
  width: 30rem;
  background-color: white;
}
.h {
  font-size: 1.25rem;
}
</style>
