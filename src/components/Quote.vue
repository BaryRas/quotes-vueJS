<template>
  <blockquote>
    <p>
      {{ quote.quote }}
    </p>
    <footer>
      <cite>-- {{ quote.author }}</cite>
    </footer>
  </blockquote>
</template>

<script>
export default {
  name: "Quote",
  props: {
    quote: Object
  }
};
</script>

<style scoped>
@import url("https://fonts.googleapis.com/css?family=Kristi&display=swap");
/* font-family: 'Kristi', cursive; */

blockquote {
  margin: 0;
  cursor: pointer;
  height: 150px;
  display: flex;
  flex-direction: column;
  padding: 10px;
  background: #eee;
  border-radius: 5px;
}

blockquote:hover {
  background-color: var(--color-green-transparent);
  color: var(--color-white);
}

blockquote p {
  font-family: "Kristi", cursive;
  font-size: var(--font-size-lg);
}

blockquote p::before {
  content: "\201C";
}

blockquote p::after {
  content: "\201D";
}
footer {
  text-align: right;
  margin-top: auto;
}
</style>
