<template>
  <v-navigation-drawer app v-if="isSidebar">
    <v-container>
      <v-row>
        <div class="m-10">
          <v-btn>test</v-btn>
        </div>
      </v-row>
    </v-container>
  </v-navigation-drawer>

  <v-app-bar color="primary" density="compact">
    <template v-slot:prepend>
      <v-app-bar-nav-icon @click="isSidebarActive"></v-app-bar-nav-icon>
    </template>

    <v-app-bar-title>Grafs</v-app-bar-title>

    <template v-slot:append>
      <v-btn icon="mdi-dots-vertical"></v-btn>
    </template>
  </v-app-bar>
</template>

<script>
import { ref } from "vue";

export default {
  setup() {
    const isSidebar = ref(true);

    const isSidebarActive = () => {
      if (isSidebar.value) {
        isSidebar.value = false;
      } else {
        isSidebar.value = true;
      }
    };

    return { isSidebar, isSidebarActive };
  },
};
</script>

<style></style>
