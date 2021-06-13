<template>
  <div id="app">
    <h3>{{title}}</h3>
    <div class="col-md-12">
      <calculation />
    </div>
  </div>
</template>

<script>
import calculation from './components/Calculation.vue'

export default {
  name: 'app',
  data() {
    return {
      title: "Calculator",
    }
  },
  components: {
    calculation
  }
}
</script>
