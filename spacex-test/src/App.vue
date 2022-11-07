<template>
  <main>
    <div class="row">
      <Month title="January" :number-of-days="getNumberOfDaysForMonth(1)" :month-number="'01'" />
      <Month title="February" :number-of-days="getNumberOfDaysForMonth(2)" :month-number="'02'" />
      <Month title="March" :number-of-days="getNumberOfDaysForMonth(3)" :month-number="'03'" />
      <Month title="April" :number-of-days="getNumberOfDaysForMonth(4)" :month-number="'04'" />
    </div>
    <div class="row">
      <Month title="May" :number-of-days="getNumberOfDaysForMonth(5)" :month-number="'05'" />
      <Month title="June" :number-of-days="getNumberOfDaysForMonth(6)" :month-number="'06'" />
      <Month title="July" :number-of-days="getNumberOfDaysForMonth(7)" :month-number="'07'" />
      <Month title="August" :number-of-days="getNumberOfDaysForMonth(8)" :month-number="'08'" />
    </div>
    <div class="row">
      <Month title="September" :number-of-days="getNumberOfDaysForMonth(9)" :month-number="'09'" />
      <Month title="October" :number-of-days="getNumberOfDaysForMonth(10)" :month-number="'10'" />
      <Month title="November" :number-of-days="getNumberOfDaysForMonth(11)" :month-number="'11'" />
      <Month title="December" :number-of-days="getNumberOfDaysForMonth(12)" :month-number="'12'" />
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
    }
  },
}
</script>

<style scoped>

</style>
