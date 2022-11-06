<template>
  <span class="date">{{dateNumber}}</span>
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
      type: String,
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
.date {
  width: 100%;
  float: left;
  text-align: center;
}

.launch-date {
  background-color: lightblue;
}
</style>
