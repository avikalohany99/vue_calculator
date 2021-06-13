<template>
  <div id="app">
    <div class="col-md-6">
      <div class="calc-card center">
        <h4 id="title">
          {{title}}
        </h4>
        <div id="screen">"Type here"
        <calculation />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import calculation from './components/Calculation.vue'

export default {
  name: 'app',
  data() {
    return {
      title: "CALCULATOR",
    }
  },
  components: {
    calculation
  }
}
</script>
