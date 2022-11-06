<template>
  <h1>A Date</h1>
  <p>dateNumber: {{dateNumber}}</p>
  <p>dateUtc: {{dateUtc}}</p>
  <p>launch: {{launch}}</p>
</template>

<script>
export default {
  name: 'Date',
  props: {
    dateNumber: {
      type: Number,
      required: true
    },
    dateUtc: {
      type: Date,
      required: false,
      default: null
    },
    launch: {
      type: Object,
      required: false,
      default: null
    }
  }
}
</script>

<style scoped>
</style>
