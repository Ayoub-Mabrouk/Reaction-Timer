<template>
  <div class="block" v-if="showBlock" @click="stopTimer">CLICK ME</div>
</template>

<script>
export default {
  props: ['delay'],
  data() {
    return {
      showBlock: false,
      timer: null,
      reactionTime: 0
    }
  },
  mounted() {
    setTimeout(() => {
      this.showBlock = true
      this.startTimer()
    }, this.delay)
  },
  methods: {
    startTimer() {
      this.timer = setInterval(() => {
        this.reactionTime += 10
      }, 10)
    },
    stopTimer() {
      clearInterval(this.timer)
      this.$emit('end',this.reactionTime)

    }
  }
};
</script>

<style>
.block {
  transition:300ms;
  font-size: 50px;
  width: 400px;
  border-radius: 20px;
  background: #5e6394;
  color: white;
  text-align: center;
  padding: 80px 0;
  margin: 40px auto;
}
.block:hover {
  font-size: 50px;
  width: 400px;
  border-radius: 20px;
  background: #3f4266;
  color: white;
  text-align: center;
  padding: 80px 0;
  margin: 40px auto;
}
</style>