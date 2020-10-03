<template>
  <div>
    <!-- <v-container
      ><h1>{{ word }} |</h1>
      <h4>Part of speech : {{ partOfSpeech }}</h4>
      <h3>Meaning : {{ mean }}</h3>
      Example: {{ ex }}</v-container
    > -->
    <v-card class="mx-auto" color="#EEEED1" max-width="850">
      <v-card-text>
        <div>Dict</div>
        <p class="display-1 text--primary">
          {{ word }}
        </p>
        <p>Part of speech : {{ partOfSpeech }}</p>
        <div class="text--primary">
          <b>Meaning :</b> {{ mean }}<br />
          <b>Example:</b> {{ ex }}
        </div>
      </v-card-text>
      <v-card-actions>
        <v-btn text color="blue accent-4" to="/shop"> Search </v-btn>
      </v-card-actions>
    </v-card>
  </div>
</template>


<script>
export default {
  data() {
    return {
      word: this.$route.params.id.word,
      mean: this.$route.params.id.meanings[0].definitions[0].definition,
      partOfSpeech: this.$route.params.id.meanings[0].partOfSpeech,
      ex: this.$route.params.id.meanings[0].definitions[0].example,
    };
    console.log();
  },
};
</script>

<style>
</style>
