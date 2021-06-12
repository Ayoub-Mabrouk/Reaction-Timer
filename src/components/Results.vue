<template>
  <p>Reaction Time - {{ score }} ms</p>
  <p class="rank">- {{ rank }}</p>
</template>

<script>
export default {
  props: ["score"],
  data() {
    return {
      rank: null,
    };
  },
  mounted() {
    this.rank =
      this.score < 175
        ? "You Are Extremely FAST" +
          String.fromCodePoint(128580) +
          String.fromCodePoint(128552)
        : this.score < 225
        ? "You are Faster than the average" + String.fromCodePoint(128515)
        : this.score < 275
        ? "You Are Around average " + String.fromCodePoint(128515)
        : "You Got Snail's Speed" + String.fromCodePoint(128514)+String.fromCodePoint(128012);
  },
};
</script>

<style>
.rank {
  font-size: 1.4em;
  color: 0faf87;
  font-weight: bold;
}
</style>