<template>
  <div>
    <div class="col-md-6">
      <div class="calc-card center">
        <h4 id="title">CALCULATOR</h4>
        <div id="screen">{{ current_calc || 0 }}</div>
        <div class="calculator__keys">
          <button @click="append('7')">7</button>
          <button @click="append('8')">8</button>
          <button @click="append('9')">9</button>
          <button class="operator" @click="div_num">/</button>
          <div class="break"></div>
        </div>
        <div class="calculator__keys">
          <button @click="append('4')">4</button>
          <button @click="append('5')">5</button>
          <button @click="append('6')">6</button>
          <button class="operator" @click="mul_num">x</button>
          <div class="break"></div>
        </div>
        <div class="calculator__keys">
          <button @click="append('1')">1</button>
          <button @click="append('2')">2</button>
          <button @click="append('3')">3</button>
          <button class="operator" @click="sub_num">-</button>
          <div class="break"></div>
        </div>
        <div class="calculator__keys">
          <button @click="append('0')">0</button>
          <button class="btn_clr" @click="clr_display()">AC</button>
          <button class="operator" @click="eql">=</button>
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
      current_calc: "",
      result1: null,
      result2: null,
      operator: null,
      operatorClicked1: false,
      operatorClicked2: false,
    };
  },
  methods: {
    clr_display() {
      this.current_calc = "";
    },
    append(num) {
      if (this.operatorClicked) {
        this.current_calc = "";
        this.operatorClicked = false;
      }
      this.current_calc = `${this.current_calc}${num}`;
    },
    add_num() {
      this.operator = (num1, num2) => num1 + num2;
      this.append("+");
      this.result1 = this.current_calc;
      this.operatorClicked = true;
    },
    sub_num() {
      this.operator = (num1, num2) => num1 - num2;
      this.append("-");
      this.result1 = this.current_calc;
      this.operatorClicked = true;
    },
    mul_num() {
      this.operator = (num1, num2) => num1 * num2;
      this.append("*");
      this.result1 = this.current_calc;
      this.operatorClicked = true;
    },
    div_num() {
      this.operator = (num1, num2) => num1 / num2;
      this.append("/");
      this.result1 = this.current_calc;
      this.operatorClicked = true;
    },
    eql() {
      this.current_calc = `${this.operator(
        parseInt(this.result1),
        parseInt(this.current_calc)
      )}`;
      this.result1 = null;
    },
  },
};
</script>
