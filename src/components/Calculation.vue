<template>
<div>
    <div class="col-md-6">
      <div class="calc-card center">
        <h4 id="title">CALCULATOR</h4>
        <div id="screen">{{ current_calc || 0}}</div>
        <div class="calculator__keys">
          <button @click="num_display('7')">7</button>
          <button @click="num_display('8')">8</button>
          <button @click="num_display('9')">9</button>
          <button class="operator">/</button>
          <div class="break"></div>
        </div>
        <div class="calculator__keys">
          <button @click="num_display('4')">4</button>
          <button @click="num_display('5')">5</button>
          <button @click="num_display('6')">6</button>
          <button class="operator">x</button>
          <div class="break"></div>
        </div>
        <div class="calculator__keys">
          <button @click="num_display('1')">1</button>
          <button @click="num_display('2')">2</button>
          <button @click="num_display('3')">3</button>
          <button class="operator">-</button>
          <div class="break"></div>
        </div>
        <div class="calculator__keys">
          <button @click="num_display('0')">0</button>
          <button class="btn_clr" @click="clr_display()">AC</button>
          <button class="operator">=</button>
          <button class="operator" @click="add_num">+</button>
          <div class="break"></div>
          
        </div>
      </div>
    </div>
</div>
</template>

<script>
export default {
    data() {
        return {
            current_calc: '',
        }
    },
    methods: {
        num_display(num) {
                this.current_calc = `${this.current_calc}${num}`;
        },
        clr_display() {
                this.current_calc = '';
        },
        add_num() {
                this.current_calc.append('+');
        }
    }
}
</script>