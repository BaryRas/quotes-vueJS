<template>
  <section>
    <h2>Quotes Added</h2>

    <ol class="progress-bar">
      <li class="is-active"><span>Num quote</span></li>
      <!-- class="is-complete" -->
      <li v-bind:class="getClass(quotes, 1)"><span>1/10</span></li>
      <li v-bind:class="getClass(quotes, 2)"><span>2/10</span></li>
      <li v-bind:class="getClass(quotes, 3)"><span>3/10</span></li>
      <li v-bind:class="getClass(quotes, 4)"><span>4/10</span></li>
      <li v-bind:class="getClass(quotes, 5)"><span>5/10</span></li>
      <li v-bind:class="getClass(quotes, 6)"><span>6/10</span></li>
      <li v-bind:class="getClass(quotes, 7)"><span>7/10</span></li>
      <li v-bind:class="getClass(quotes, 8)"><span>8/10</span></li>
      <li v-bind:class="getClass(quotes, 9)"><span>9/10</span></li>
      <li v-bind:class="getClass(quotes, 10)"><span>10/10</span></li>
    </ol>
  </section>
</template>

<script>
export default {
  name: "Header",
  props: ["quotes"],
  // data() {
  //   return {
  //     checked: "quotes"
  //   };
  // },
  methods: {
    getClass(quote, num) {
      const bol = quote.length === num;
      return {
        "is-active": bol,
        "is-complete": quote.length >= num
      };
    }
  }
};
</script>

<style scoped>
h2 {
  color: var(--color-gray);
  font-size: var(--font-size-small);
  line-height: 1.5;
  font-weight: 400;
  text-transform: uppercase;
  letter-spacing: 3px;
}

.progress-bar {
  display: flex;
  justify-content: space-between;
  list-style: none;
  padding: 0;
  margin: 0 0 1rem 0;
}
.progress-bar li {
  flex: 2;
  position: relative;
  padding: 0 0 14px 0;
  font-size: var(--font-size-default);
  line-height: 1.5;
  color: var(--color-green);
  font-weight: 600;
  white-space: nowrap;
  overflow: visible;
  min-width: 0;
  text-align: center;
  border-bottom: 2px solid var(--color-gray-disabled);
}
.progress-bar li:first-child,
.progress-bar li:last-child {
  flex: 1;
}
.progress-bar li:last-child {
  text-align: right;
}
.progress-bar li:before {
  content: "";
  display: block;
  width: 8px;
  height: 8px;
  background-color: var(--color-gray-disabled);
  border-radius: 50%;
  border: 2px solid var(--color-white);
  position: absolute;
  left: calc(50% - 6px);
  bottom: -7px;
  z-index: 3;
  transition: all 0.2s ease-in-out;
}
.progress-bar li:first-child:before {
  left: 0;
}
.progress-bar li:last-child:before {
  right: 0;
  left: auto;
}
.progress-bar span {
  transition: opacity 0.3s ease-in-out;
}
.progress-bar li:not(.is-active) span {
  opacity: 0;
}
.progress-bar .is-complete:not(:first-child):after,
.progress-bar .is-active:not(:first-child):after {
  content: "";
  display: block;
  width: 100%;
  position: absolute;
  bottom: -2px;
  left: -50%;
  z-index: 2;
  border-bottom: 2px solid var(--color-green);
}
.progress-bar li:last-child span {
  width: 200%;
  display: inline-block;
  position: absolute;
  left: -100%;
}

.progress-bar .is-complete:last-child:after,
.progress-bar .is-active:last-child:after {
  width: 200%;
  left: -100%;
}

.progress-bar .is-complete:before {
  background-color: var(--color-green);
}

.progress-bar .is-active:before,
.progress-bar li:hover:before,
.progress-bar .is-hovered:before {
  background-color: var(--color-white);
  border-color: var(--color-green);
}
.progress-bar li:hover:before,
.progress-bar .is-hovered:before {
  transform: scale(1.33);
}

.progress-bar li:hover span,
.progress-bar li.is-hovered span {
  opacity: 1;
}

.progress-bar:hover li:not(:hover) span {
  opacity: 0;
}

.x-ray .progress-bar,
.x-ray .progress-bar li {
  border: 1px dashed red;
}

.progress-bar .has-changes {
  opacity: 1 !important;
}
.progress-bar .has-changes:before {
  content: "";
  display: block;
  width: 8px;
  height: 8px;
  position: absolute;
  left: calc(50% - 4px);
  bottom: -20px;
  background-image: url("data:image/svg+xml;charset=utf-8,%3Csvg%20xmlns%3D%22http%3A%2F%2Fwww.w3.org%2F2000%2Fsvg%22%20viewBox%3D%220%200%208%208%22%3E%3Cpath%20fill%3D%22%23ed1c24%22%20d%3D%22M4%200l4%208H0z%22%2F%3E%3C%2Fsvg%3E");
}
</style>
