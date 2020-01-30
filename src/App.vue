<template>
  <div id="app">
    <Header></Header>
    <AddQuote></AddQuote>
    <QuotesList></QuotesList>
    <Footer></Footer>
  </div>
</template>

<script>
import Header from "./components/Header.vue";
import AddQuote from "./components/AddQuote.vue";
import QuotesList from "./components/QuotesList.vue";
import Footer from "./components/Footer.vue";
export default {
  name: "app",
  components: {
    Header,
    AddQuote,
    QuotesList,
    Footer
  }
};
</script>

<style>
:root {
  --color-white: #fff;
  --color-black: #333;
  --color-gray: #75787b;
  --color-gray-light: #bbb;
  --color-gray-disabled: #e8e8e8;
  --color-green: #53a318;
  --color-green-transparent: #52a31877;
  --color-green-dark: #383;
  --font-size-small: 0.75rem;
  --font-size-default: 0.875rem;
}
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  padding: 0 20px;
}
</style>
