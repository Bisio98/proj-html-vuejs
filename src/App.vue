<template>
  <div id="app">
    <Header />
    <Body />
    <Footer />
  </div>
</template>

<script>
import Header from "./components/Header.vue";
import Footer from "./components/Footer.vue";
import Body from "./components/Body.vue";

export default {
  name: "App",
  components: {
    Header,
    Footer,
    Body,
  },
};
</script>

<style lang="scss">
@import "./style/general.scss";
</style>
