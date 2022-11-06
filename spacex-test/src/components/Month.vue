<template>
  <div class="month">
    <h3>{{title}}</h3>
    <p>numberOfDays: {{numberOfDays}}</p>
    <Date date-number="1" date-utc="2006-03-24T22:30:00.000Z" launch="{}"/>
  </div>
</template>

<script>
import Date from './Date.vue';

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
.month {
  width: 25%;
  float: left;
}
</style>