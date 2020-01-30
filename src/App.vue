<template>
  <div id="app">
    <Header :quotes="quotes"></Header>
    <AddQuote @addedQuote="newQuote"></AddQuote>
    <QuotesList :quotes="quotes" @del-quote="delQuote"></QuotesList>
    <Footer></Footer>
  </div>
</template>

<script>
import Header from "./components/Header.vue";
import AddQuote from "./components/AddQuote.vue";
import QuotesList from "./components/QuotesList.vue";
import Footer from "./components/Footer.vue";
import uuid from "uuid";

export default {
  name: "app",
  components: {
    Header,
    AddQuote,
    QuotesList,
    Footer
  },
  data() {
    return {
      quotes: [
        {
          id: uuid.v4(),
          author: "fdsfsd",
          quote: "Lorem, ipsum dolor sit amet consectetur adipisicing elit.",
          isCompleted: true
        }
      ],
      maxQuotes: 10
    };
  },
  methods: {
    newQuote(quote) {
      const newQuote = {
        id: uuid.v4(),
        author: "Author : " + uuid.v4(),
        quote: quote,
        isCompleted: true
      };
      if (this.quotes.length <= 9) {
        this.quotes.push(newQuote);
      } else {
        alert("Your quotes are 10/10");
      }
    },
    delQuote(id) {
      this.quotes = this.quotes.filter(quote => quote.id !== id);
    }
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
  --font-size-lg: 1.2rem;
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
