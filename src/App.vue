<script>
import AppHeader from "./components/appHeader.vue";

import AppMain from "./components/appMain.vue";

import AppFooter from "./components/appFooter.vue";

import axios from "axios";


export default {
  name: "app",
  components: {
    AppHeader,
    AppMain,
    AppFooter,
  },
  data() {
    return {
      modal: false
    };
  },
  methods: {

  },
  created() {
    axios.get('https://127.0.0.1:8000/api/projects').then((res) => {
        store.projects = res.data.results.data;
    });
  }
}

</script>

<template>
  <AppHeader />
  <AppMain :brands="brands"></AppMain>
  <AppFooter />
  <appModal />
  </template>

<style lang="scss">
@use "./style/general.scss";
</style>
