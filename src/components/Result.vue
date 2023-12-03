<template>
  <div class="result">
    <div class="title">{{ results[resultIdx].title }}</div>
    <div class="desc">{{ results[resultIdx].desc }}</div>
  </div>
</template>

<script>
export default {
  props: ["results", "totalCorrect"],
  computed: {
    resultIdx() {
      let idx = 0;
      this.results.forEach((el, i) => {
        if (el.min <= this.totalCorrect && el.max >= this.totalCorrect) {
          idx = i;
        }
      });
      return idx;
    },
  },
};
</script>
