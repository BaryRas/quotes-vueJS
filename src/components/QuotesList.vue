<template>
  <div class="quotes-list">
    <div v-for="quote in quotes" :key="quote.id">
      <Quote
        :quote="quote"
        @click.native="$emit('del-quote', quote.id)"
      ></Quote>
      <!-- native = take the html code of the component -->
    </div>
  </div>
</template>

<script>
import Quote from "./Quote";
export default {
  name: "QuotesList",
  props: ["quotes"],
  components: {
    Quote
  }
};
</script>

<style scoped>
.quotes-list {
  display: grid;
  grid-template-rows: repeat(2, 200px);
  grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
  grid-gap: 10px;
  grid-auto-rows: 200px;
}
</style>
