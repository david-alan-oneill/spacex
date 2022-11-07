<template>
  <main>
    <h2>Click a date to view more information about launch</h2>
    <div class="row">
      <Month title="January" :number-of-days="getNumberOfDaysForMonth(1)" :month-number="'01'" @viewLaunchData="viewLaunchData" />
      <Month title="February" :number-of-days="getNumberOfDaysForMonth(2)" :month-number="'02'" @viewLaunchData="viewLaunchData" />
      <Month title="March" :number-of-days="getNumberOfDaysForMonth(3)" :month-number="'03'" @viewLaunchData="viewLaunchData" />
      <Month title="April" :number-of-days="getNumberOfDaysForMonth(4)" :month-number="'04'" @viewLaunchData="viewLaunchData" />
    </div>
    <div class="row">
      <Month title="May" :number-of-days="getNumberOfDaysForMonth(5)" :month-number="'05'" @viewLaunchData="viewLaunchData" />
      <Month title="June" :number-of-days="getNumberOfDaysForMonth(6)" :month-number="'06'" @viewLaunchData="viewLaunchData" />
      <Month title="July" :number-of-days="getNumberOfDaysForMonth(7)" :month-number="'07'" @viewLaunchData="viewLaunchData" />
      <Month title="August" :number-of-days="getNumberOfDaysForMonth(8)" :month-number="'08'" @viewLaunchData="viewLaunchData" />
    </div>
    <div class="row">
      <Month title="September" :number-of-days="getNumberOfDaysForMonth(9)" :month-number="'09'" @viewLaunchData="viewLaunchData" />
      <Month title="October" :number-of-days="getNumberOfDaysForMonth(10)" :month-number="'10'" @viewLaunchData="viewLaunchData" />
      <Month title="November" :number-of-days="getNumberOfDaysForMonth(11)" :month-number="'11'" @viewLaunchData="viewLaunchData" />
      <Month title="December" :number-of-days="getNumberOfDaysForMonth(12)" :month-number="'12'" @viewLaunchData="viewLaunchData" />
    </div>
  </main>
</template>

<script>
import Month from './components/Month.vue'

export default {
  name: 'App',
  components: {
    Month
  },
  methods: {
    getNumberOfDaysForMonth(month) {
      const year = new Date().getFullYear();
      return new Date(year, month, 0).getDate();
    },
    viewLaunchData(launchData) {
      const body = "ID: "+ launchData.id +"\nName: " + launchData.name + "\nDate: " + launchData.date_utc + "\nFlight Number: " + launchData.flight_number
      alert(body);
    }
  },
}
</script>

<style scoped>

</style>
