<template>
  <v-navigation-drawer app v-if="isSidebar">
    <v-container fluid>
      <v-row>
        <template v-for="pref in prefData" :key="pref.prefCode">
          <v-col cols="6">
            <v-checkbox :label="pref.prefName" color="primary" hide-details></v-checkbox>
          </v-col>
        </template>
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
import axios from "axios";
import api from "../plugins/resas.js";

export default {
  setup() {
    const isSidebar = ref(true);
    const prefData = [];

    const isSidebarActive = () => {
      if (isSidebar.value) {
        isSidebar.value = false;
      } else {
        isSidebar.value = true;
      }
    };

    axios
      .get("https://opendata.resas-portal.go.jp/api/v1/prefectures", { headers: { "X-API-KEY": api.key } })
      .then((res) => {
        prefData.push(...res.data.result);
      });

    return { prefData, isSidebar, isSidebarActive };
  },
};
</script>

<style></style>
