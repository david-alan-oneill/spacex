<template>
  <h1>A Month</h1>
  <Date></Date>
</template>

<script setup>
import Date from './Date.vue'

export default {
  name: 'Month',
  components: {
    Date
  },
  props: {
    title: {
      type: String,
      required: true
    },
    numberOfDays: {
      type: Number,
      required: true
    },
    launches: {
      type: Array,
      required: false,
      default: null
    }
  }
}
</script>

<style scoped>

</style>