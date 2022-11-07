<template>
  <span class="date" :class="isLaunchDate ? 'launch-date' : '', isUpComing ? 'launch-upcoming' : ''" @click="displayLaunchData">{{dateNumber}}</span>
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
  methods: {
    displayLaunchData() {
      if (this.launch) {
        const launchData = {
          'id': this.launch.id,
          'name': this.launch.name,
          'date_utc': new Date(this.launch.date_utc).toDateString() + ' ' + new Date(this.launch.date_utc).toLocaleTimeString() ,
          'flight_number': this.launch.flight_number
        };

        this.$emit('viewLaunch', launchData);
      }
    }
  },
  data() {
    return {
      isLaunchDate: false,
      isUpComing: false
    }
  },
  created() {
    if (this.launch) {
      if (this.launch.upcoming) {
        this.isUpComing = true;
      } else {
        this.isLaunchDate = true;
      }
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
  border-radius: 20px;
}

.launch-upcoming {
  background-color: lightgray;
  border-radius: 20px;
}
</style>
