<template>
  <div class="quotes-list">
    <div v-for="quote in quotes" :key="quote.id">
      <Quote :quote="quote"></Quote>
    </div>
  </div>
</template>

<script>
import uuid from "uuid";
import Quote from "./Quote";
export default {
  name: "QuotesList",
  data() {
    return {
      quotes: [
        {
          id: uuid.v4(),
          author: "fdsfsd",
          quote: "Lorem, ipsum dolor sit amet consectetur adipisicing elit."
        },
        {
          id: uuid.v4(),
          author: "fdsfsd-fdsfsd-fdsfsd",
          quote:
            "Lorem, ipsum dolor sit amet consectetur adipisicing elit. Optio a quidem blanditiis iste quae quod quis. At atque molestias inventore ullam explicabo, autem eaque"
        },
        {
          id: uuid.v4(),
          author: "fdsfsd",
          quote:
            "Lorem, ipsum dolor sit amet consectetur adipisicing elit. cupiditate nostrum, expedita quod quisquam doloribus consequatur molestias? Veniam vero et dolorum eius voluptate obcaecati similique doloribus nam quam?"
        },
        {
          id: uuid.v4(),
          author: "fdsfsd",
          quote:
            "Lorem, ipsum dolor sit amet consectetur adipisicing elit. Lorem, ipsum dolor sit amet consectetur adipisicing elit."
        },
        {
          id: uuid.v4(),
          author: "fdsfsd",
          quote:
            "Lorem, ipsum dolor sit ametLorem, ipsum dolor sit amet consectetur adipisicing elit. consectetur adipisicing elit."
        },
        {
          id: uuid.v4(),
          author: "fdsfsd",
          quote: "Lorem, ipsum dolor sit amet consectetur adipisicing elit."
        },
        {
          id: uuid.v4(),
          author: "fdsfsd",
          quote:
            "Lorem, ipsum dolor sit amet consectetur Lorem, ipsum dolor sit amet consectetur adipisicing elit. adipisicing elit."
        },
        {
          id: uuid.v4(),
          author: "fdsfsd",
          quote:
            "Lorem, ipsum dolor sitLorem, ipsum dolor sit amet consectetur adipisicing elit. amet consectetur adipisicing elit."
        },
        {
          id: uuid.v4(),
          author: "fdsfsd",
          quote:
            "Lorem, ipsum dolor sit amet Lorem, ipsum dolor sit amet consectetur adipisicing elit.consectetur adipisicing elit."
        },
        {
          id: uuid.v4(),
          author: "fdsfsd",
          quote:
            "Lorem, ipsum Lorem, ipsum dolor sit amet consectetur adipisicing elit.dolor Lorem, ipsum dolor sit amet consectetur adipisicing elit.sit amet consectetur adipisicing elit."
        }
      ]
    };
  },

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
