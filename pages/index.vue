<template>
  <v-row justify="center" align="center">
    <v-col cols="12" sm="8" md="9">
      <div class="text-center">
        <vuetify-logo />
        <h1 class="mt-5 mb-5">Welcome to Dictionary Search</h1>
        <v-btn class="mt-5" color="primary" nuxt to="/shop"> Continue </v-btn>
      </div>
    </v-col>
  </v-row>
</template>

<script>
import VuetifyLogo from "~/components/VuetifyLogo.vue";

export default {
  components: {
    VuetifyLogo,
  },
};
</script>
