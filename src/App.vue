<template>
  <v-app>
    <NavBar />
    <v-main>
      <TopFront />
    </v-main>
  </v-app>
</template>

<script>
import TopFront from "./pages/TopFront.vue";
import NavBar from "./components/NavBar.vue";

export default {
  name: "App",

  components: {
    TopFront,
    NavBar,
  },

  data: () => ({
    //
  }),
};
</script>
