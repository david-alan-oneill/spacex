<template>
  <div class="month">
    <h3 class="month-title">{{title}}</h3>
    <div class="row" v-for="week in weeks">
      <Date v-for="date in week" :date-number="date.number" />
    </div>
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
  },
  data() {
    return {
      weeks: []
    }
  },
  created() {
    let week = 0;
    let dates = [];

    for(let count = 0; count < this.numberOfDays; count ++) {
      let dayCount = count + 1;
      dates.push({number: dayCount});

      if (dayCount % 7 === 0) {
        this.weeks[week] = dates;
        week ++;
        dates = [];
      }
    }
  }
}
</script>

<style scoped>
.month {
  width: 25%;
  float: left;
  margin-top: 20px;
}

.month-title {
  margin-bottom: 10px;
  margin-top: 20px;
}
</style>