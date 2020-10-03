<template>
  <v-layout>
    <v-flex class="text-center">
      <img
        src="https://icons.iconarchive.com/icons/oxygen-icons.org/oxygen/256/Apps-accessories-dictionary-icon.png"
        alt="Vuetify.js"
        class="mb-5"
      />
      <v-container class="center"
        ><input type="text" class="datee" v-model="keyword" />
        <button class="button" @click="search()">Search</button></v-container
      >

      <v-container v-if="result" class="center">
        <v-card class="mx-auto" max-width="500">
          <v-card-text>
            <p class="display-1 text--primary">
              <nuxt-link
                :to="{
                  name: 'shop-id',
                  params: { id: result },
                }"
                ><h1>{{ result.word }}</h1>
              </nuxt-link>
            </p>
            <p>{{ text }}</p>
            <div class="text--primary">
              {{ men }}
            </div>
          </v-card-text>
        </v-card></v-container
      >
    </v-flex>
  </v-layout>
</template>
<script>
import axios from "axios";
export default {
  data() {
    return {
      result: "",
      sound: "",
      text: "",
      men: "",
    };
  },
  methods: {
    search() {
      axios
        .get("https://api.dictionaryapi.dev/api/v2/entries/en/" + this.keyword)
        .then((res) => {
          this.result = res.data[0];
          this.text = res.data[0].phonetics[0].text;
          this.men = res.data[0].meanings[1].definitions[0].definition;
          console.log(this.men);
        })

        .catch((err) => {
          console.error(err);
        });
    },
  },
};
</script>

<style>
.box {
  margin-left: auto;
}
.button {
  background-color: rgb(255, 116, 116);
  border: none;
  color: rgb(255, 255, 255);
  padding: 5px 5px 5px 5px;
  text-align: center;
  display: inline-block;
  margin: 10px 5px;
  font-size: 2rem;
  cursor: pointer;
  border-radius: 12px;
  border: 0.5px solid rgb(255, 183, 149);
  width: 10rem;
}
button:hover {
  color: rgb(255, 140, 140);
  border: 0.5px solid rgba(0, 0, 0, 0.575);
  background-color: rgba(0, 0, 0, 0.527);
}

.bo {
  color: white;
  font-size: 50px;
}
.datee {
  border-radius: 8px;
  padding: 12px;
  border: 2px solid #c2baba;
  font-size: 20px;
  width: 30rem;
  background-color: white;
}
</style>
