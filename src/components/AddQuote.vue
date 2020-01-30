<template>
  <div>
    <form class="addQuote">
      <label>Quote</label>
      <textarea
        type="text"
        v-model="quote"
        placeholder="Enter your Quote here..."
      >
      </textarea>
      <div>
        <button type="submit" @click.prevent="addQuote">Add Quote</button>
        <!-- <input type="submit" value="Submit" class="btn submit" /> -->
        <p>Add input for the author next time</p>
      </div>
    </form>
  </div>
</template>

<script>
// import { eventBus } from "../main.js";
// import uuid from "uuid";

export default {
  name: "AddQuotes",
  data() {
    return {
      quote: ""
    };
  },
  methods: {
    addQuote() {
      this.$emit("addedQuote", this.quote);
      this.quote = "";
    }
  }
};
</script>

<style scoped>
.addQuote {
  display: flex;
  flex-direction: column;
  /* justify-content: center; */
  width: 60vw;
  margin: 50px auto;
}
h2 {
  color: var(--color-gray);
  font-size: var(--font-size-default);
  line-height: 1.5;
  font-weight: 400;
  text-transform: uppercase;
  letter-spacing: 3px;
  /* margin-top: 50px; */
}
textarea {
  width: 50vw;
  height: 10vh;
  align-self: center;
  margin: 20px 0;
}
input:focus,
textarea:focus {
  outline-color: var(--color-green);
}

button {
  padding: 10px 25px;
  width: 25vw;
  background-color: var(--color-green-dark);
  /* border: none; */
  border-radius: 5px;
  color: var(--color-grey);
  cursor: pointer;
  align-self: center;
}

button:hover {
  background-color: var(--color-green);
  color: var(--color-white);
}
</style>
