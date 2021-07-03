<template>
  <div class="results">
    <slot name="contents"></slot>
  </div>
</template>

<script>
  export default {
    props: ['score'],
    mounted() {
      this.getPlayerSpeed(this.score)
    },
    methods: {
      getPlayerSpeed(score) {
        if (score <= 400) {
          this.$emit('gameResults', 'Rapid Reflexes')
        }
        else {
          this.$emit('gameResults', '...Snail Pace')
        }
      }
    }
  }
</script>

<style scoped>

  .results h2 {
    color: #0faf87
  }

</style>