<template>
  <main>
    <div class="row">
      <Month title="January" number-of-days="1"/>
      <Month title="February" number-of-days="1"/>
      <Month title="March" number-of-days="1"/>
      <Month title="April" number-of-days="1"/>
    </div>
    <div class="row">
      <Month title="May" number-of-days="1"/>
      <Month title="June" number-of-days="1"/>
      <Month title="July" number-of-days="1"/>
      <Month title="August" number-of-days="1"/>
    </div>
    <div class="row">
      <Month title="September" number-of-days="1"/>
      <Month title="October" number-of-days="1"/>
      <Month title="November" number-of-days="1"/>
      <Month title="December" number-of-days="1"/>
    </div>
  </main>
</template>

<script>
import Month from './components/Month.vue'

export default {
  name: 'App',
  components: {
    Month
  }
}
</script>

<style scoped>

</style>
