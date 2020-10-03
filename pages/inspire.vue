<template>
  <v-layout>
    <v-flex class="text-center">
      <img src="/v.png" alt="Vuetify.js" class="mb-5" />
      <blockquote class="blockquote">
        &#8220;First, solve the problem. Then, write the code.&#8221;
        <footer>
          <small>
            <em>&mdash;John Johnson</em>
          </small>
         
            <input type="text" v-model="keyword" />
            <v-btn color="primary"> Primary </v-btn>
           
        </footer>
      </blockquote>
    </v-flex>
  </v-layout>
</template>
