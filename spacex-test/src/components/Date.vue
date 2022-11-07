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
    launch: {
      type: Object,
      required: false,
      default: null
    }
  },
  created() {
    // if (this.launch) {
      console.log(this.launch);
    // }
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
