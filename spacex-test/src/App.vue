<template>
  <main>
    <div class="row">
      <Month title="January" :number-of-days="getNumberOfDaysForMonth(1)"/>
      <Month title="February" :number-of-days="getNumberOfDaysForMonth(2)"/>
      <Month title="March" :number-of-days="getNumberOfDaysForMonth(3)"/>
      <Month title="April" :number-of-days="getNumberOfDaysForMonth(4)"/>
    </div>
    <div class="row">
      <Month title="May" :number-of-days="getNumberOfDaysForMonth(5)"/>
      <Month title="June" :number-of-days="getNumberOfDaysForMonth(6)"/>
      <Month title="July" :number-of-days="getNumberOfDaysForMonth(7)"/>
      <Month title="August" :number-of-days="getNumberOfDaysForMonth(8)"/>
    </div>
    <div class="row">
      <Month title="September" :number-of-days="getNumberOfDaysForMonth(9)"/>
      <Month title="October" :number-of-days="getNumberOfDaysForMonth(10)"/>
      <Month title="November" :number-of-days="getNumberOfDaysForMonth(11)"/>
      <Month title="December" :number-of-days="getNumberOfDaysForMonth(12)"/>
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
