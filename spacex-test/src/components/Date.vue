<template>
  <span class="date" :class="isLaunchDate ? 'launch-date' : ''">{{dateNumber}}</span>
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
  data() {
    return {
      isLaunchDate: false
    }
  },
  created() {
    if (this.launch) {
      this.isLaunchDate = true;
    }
  }
}
</script>

<style scoped>
.date {
  width: 10%;
  float: left;
  text-align: center;
}

.launch-date {
  background-color: lightblue;
}
</style>
