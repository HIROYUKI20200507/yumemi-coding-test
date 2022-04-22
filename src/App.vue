<template>
  <v-app>
    <v-main>
      <TopFront />
    </v-main>
  </v-app>
</template>

<script>
import TopFront from "./pages/TopFront.vue";

export default {
  name: "App",

  components: {
    TopFront,
  },

  data: () => ({
    //
  }),
};
</script>
