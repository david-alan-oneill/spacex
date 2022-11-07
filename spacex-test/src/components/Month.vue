<template>
  <div class="month">
    <h3 class="month-title">{{title}}</h3>
    <div class="row" v-for="week in weeks">
      <Date v-for="date in week" :key="week + date" :date-number="date.number" :launch="checkIfTodayHasLaunch(date.number)" />
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
    monthNumber: {
      type: Number,
      required: true
    },
    launches: {
      type: Array,
      required: false,
      default: null
    }
  },
  methods: {
    async fetchLaunches() {
      const gte = "2022-"+ this.monthNumber +"-01T00:00:00.000Z";
      const lte = "2022-"+ this.monthNumber +"-"+ this.numberOfDays +"T00:00:00.000Z";
      const query = JSON.stringify({
        "query": {
          "date_utc": {
            "$gte": gte,
            "$lte": lte
          }
        },
        "options": {
          "limit": this.numberOfDays
        }
      });

      const res = await fetch('https://api.spacexdata.com/v4/launches/query', {
        method: 'POST',
        headers: {'Content-Type': 'application/json'},
        body: query
      });

      const jsonRes = await res.json();
      return jsonRes.docs;
    },
    populateDocs(docs) {
      this.docs = docs;
    },
    checkIfTodayHasLaunch(dateNumber) {
      if (dateNumber.toString().length === 1) {
        dateNumber = "0" + dateNumber;
      }

      const today = "2022-" + this.monthNumber + "-" + dateNumber;
      const launches = JSON.parse(JSON.stringify(this.docs));

      launches.forEach(function (launch) {
        const dateUtc = launch.date_utc.split("T")[0];

        if (dateUtc === today) {
          console.log(launch);
          return launch;
        }
      });

      return null;
    }
  },
  data() {
    return {
      weeks: [],
      docs: []
    }
  },
  async created() {
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

    const docs = await this.fetchLaunches();
    this.populateDocs(docs);
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
  margin-left: 30px;
  margin-top: 20px;
}
</style>