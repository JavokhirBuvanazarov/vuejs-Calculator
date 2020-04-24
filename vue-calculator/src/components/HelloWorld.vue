<template>
  <main class="container">
    <div id="calculator">
      <header class="top-part">
        <div class="top">
          <h5 class="branding">Calculator</h5>
          <div class="window">
            <div class="minimize button" role="button">
              <img class="icon icons8-Minus-Math-" src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAACAAAAAgCAYAAABzenr0AAAARElEQVRYR+3V0Q0AMAQFQPYfuh1A+ql8nAF4LhIZw5XD80MAAgQIECCwVuA0fcmy8EtgPEATQG279gYIECBAgACBbwIXi38CITaYSB4AAAAASUVORK5CYII=">
            </div>
            <div class="maximize button" role="button">
              <img class="icon icons8-Rectangle" src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAACAAAAAgCAYAAABzenr0AAAAU0lEQVRYR+3WIQIAIAhDUbj/oTVpkIBlzvA9gJtPAhnmk+b8oAACp8B4NJQ799sCqtlYwq0ABRBAAAEEEEDALqBejNp9wFZAHVzuV/319UMogMAEOqwkIXyG1okAAAAASUVORK5CYII=">
            </div>
            <div class="close button" role="button">
              <img class="icon icons8-Multiply" src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAACAAAAAgCAYAAABzenr0AAABBUlEQVRYR+2W6w3CMAyErxuwCYwAG7AJjAATMQKMUDZhBHQSQaFqYp8DqpDSn2nj+3J+NAMWfoaF9dEBugN/4cAewA3AQ+yYFYADgHNtn+UAxS8ARgA7AYLiVwCbF8CpBGEBMBBPvxYgcvE7gG0N3AIguAIhiTO4B8ALIYsrABZESFwFKEFwPRWcmfNpMXpTkO+b1gTfsdpl8YgDCSSH4FpIvBUg2c446px4OxpNQZ5zBlPmxEcZqABz1c6A6rAKOVBrNWVYhRzw9HkIwpMCj/hcd7gK0wJQxEMQFkD6Hat9nqeD94Hw75inarmQHGviLYNIvByVP7dS8DWh6I2oA3QHfu7AEzfHWCF+OOmJAAAAAElFTkSuQmCC">
            </div>
          </div>
        </div>
        <div class="type">
          <div class="column menu">
            <div class="calculator-menu button-top" role="button">
              <img class="icon icons8-Menu" src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAACAAAAAgCAYAAABzenr0AAAATElEQVRYR+3TsQ0AMAgDQdh/aFIj0ZKn+AyQOCc7Az4Jvx8GUOCkQC0vo316EsADLAP06092QAEF8BniAeyAAgrgM8QD2AEFFPgq8ACF3gYho2IK1QAAAABJRU5ErkJggg==">
            </div>
            <label class="calculator-chosen">STANDARD</label>
          </div>
          <div class="column history">
            <div class="button-top" role="button">
              <img class="icon icons8-Past" src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAACAAAAAgCAYAAABzenr0AAAB4klEQVRYR+2W4U3DQAyFXyeAEWACygZsAEwAbFA2gAmACYAJgA1ggsIEMAJMAPqQXSXpxXfXRO2fWqoa5S7287PvnSfasE02HF9bALUM7Eo6k3RipTuy/3dJX5JeJb3Yc1F1SwEQ+EbSeZFX6UHSdQmQFIBfC+JrZHsvCRAYGRLg2zLm3dR+MAJDGOsXkp4j0DkAZExw7M0YgOrI9iTdSjq2TYAAcNIiAKeSnuwr6LxKeOiy1dwys7LxDl9JJiIAUAjtfcFxHAFg3UHga9/K0sojAuC0e6enKMwB4BsypxyPqSbOAegG7e4vAUBPfJojWGj10DoANFm4tAZdJFaqA31NXMIA3/pp4gi7iP37XBcAdGIuCcU8bGYzFoAUQ0X9khOijOYsjuGoAKDpwKjieQzzEnyYZIdN6Oc2lNBKVFVN6OqVFI7KwL7dkyo6hqFwrACgWoiIwe3FtQpyLpIhVi3FBAM1DbgjaYm2CjRezh/zyaXUskgHUCy/jnF0VxGYrStfx804zYEEKmGjZCBhfHPJrR5IuoniiJ6gHN4fDJ+cadcJzjnawdXtcyO081w9kqWYpieYiHzey1WDI0wJlmpe0wN9QGCETAFF1hhs+FhOxrkyhUqYy27U9aG34WAwWwB/XytsITVxIuMAAAAASUVORK5CYII=">
            </div>
          </div>
        </div>
        <div class="screen">
          <div class="history-screen">
            <p>
              {{formula}}
            </p>
          </div>
          <div class="main-screen">
            <p>{{ result }}</p>
          </div>
        </div>
        <div class="bottom">
          <div class="memory">
            <div role="button">MC</div>
            <div role="button">MR</div>
            <div role="button">M+</div>
            <div role="button">M-</div>
            <div role="button">MS</div>
            <div role="button">M&darr;</div>
          </div>
        </div>
      </header>
      <section class="bottom-part">
        <div class="features">
          <div class="main-menu">
            <div class="row">
              <div class="col numbers">
                <div @click="operate(7)" class="button number" role="button" data-value="7">7</div>
                <div @click="operate(8)" class="button number" role="button" data-value="8">8</div>
                <div @click="operate(9)" class="button number" role="button" data-value="9">9</div>
                <div @click="operate(4)" class="button number" role="button" data-value="4">4</div>
                <div @click="operate(5)" class="button number" role="button" data-value="5">5</div>
                <div @click="operate(6)" class="button number" role="button" data-value="6">6</div>
                <div @click="operate(1)" class="button number" role="button" data-value="1">1</div>
                <div @click="operate(2)" class="button number" role="button" data-value="2">2</div>
                <div @click="operate(3)" class="button number" role="button" data-value="3">3</div>
                <div @click="operate('.')" id="dot"  class="button dot sign" data-value="." role="button">.</div>
                <div @click="operate(0)" class="button number" role="button" data-value="0">0</div>
                <div @click="operate('(')"  id="bracketsLeft" class="button brackers" data-value="()" role="button">(</div>

              </div>
              <!--End col numbers-->
              <div class="col operators">
                <div @click="cleanAll" id="clear" class="button sign" data-value="C" role="button">C</div>
                <div @click="toggle" id="sign" class="button image sign" data-value="CS" role="button">±</div>
                <div @click="operate('*')" id="multiply" class="button image sign" data-value="*" role="button">*</div>
                <div @click="operate('/')" id="divide" class="button image sign" data-value="/" role="button">/</div>
                <div @click="operate('+')" id="plus" class="button image sign" data-value="+" role="button">+</div>
                <div @click="operate('-')" id="minus" class="button image sign" data-value="-" role="button">-</div>
                <div @click="operate(')')" id="bracketsRight" class="button brackers" data-value="()" role="button">)</div>
                <div @click="equal" id="equal" class="button image equals sign" data-value="=" role="button">=</div>
              </div>
              <!--End col operators-->
            </div>
            <!--End row-->
          </div>
        </div>
        </section>
      </div>
    <div class="history">
      <ul>
        <li v-for="(calculation,i) in calculations" :key="i">
          <span>{{calculation.calculation}}</span> <span style="margin-left: 20px">{{calculation.date}}</span>
        </li>
      </ul>
    </div>
  </main>

  </template>

  <script>
    import axios from 'axios';
  export default {
    name: 'HelloWorld',
    data() {
      return {
        formula: "",
        result: 0,
        operatorClicked: true,
        history:'',
        calculations: []
      }
    },


    created(){
      this.fetchdata()
    },

    methods: {
      fetchdata() {
         axios.get('https://vuejs-calculator.firebaseio.com/calculation.json')
        .then(res => this.calculations = res.data)
        .catch(err => console.log(err))
      },
      operate(element) {
        let operator = this.formula.charAt(this.formula.length-1);
        console.log(operator);
        this.formula += element;

        // console.log("this.formula:");
        // console.log(this.formula);
      },

      equal() {
        console.log("equal..");

        if (eval(this.formula) === undefined) {
          this.result = 0;
        }
        if (eval(this.formula) === Infinity) {
          this.result = 'Dividing into zero is not allowed';
        }
        this.result = eval(this.formula);
        let today = new Date("2020-04-24");
        const data = {
          calculation: this.formula,
          date: today
        }
        axios.post('https://vuejs-calculator.firebaseio.com/calculation.json',data)
          .then(res => {
            this.fetchdata()
            console.log(res)
            })
          .catch(err => console.log(err))
      },

      cleanAll() {
        console.log("cleanAll..");
        this.formula = "";
        this.result = 0;
      },

      devided() {
        console.log("devided..");
        this.formula === "" || this.formula.endsWith("+" || "-" || "*" || "/" || "%") ? {} : this.formula = "1/(" + this.formula + ")";
        this.equal();
      },

      toggle() {
        console.log("toggle..");


        this.formula === "" || this.formula.endsWith("+" || "-" || "*" || "/" || "%") ? {} : this.formula.startsWith("-") ? this.formula = Math.abs(eval(this.formula)).toString() : this.formula = "-(" + this.formula + ")";
        this.equal();
      }

    }
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  @import url(https://fonts.googleapis.com/css?family=Open+Sans:400,700);

  * {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
    -webkit-touch-callout: none;
    -webkit-user-select: none;
    -khtml-user-select: none;
    -moz-user-select: none;
    -ms-user-select: none;
    user-select: none;
  }
  .container{
    margin: 0 auto;

  }
  .history{
    margin-left: 30px;
  }
  body {
    font-family: 'Open Sans', sans-serif;
    background: url("https://pp.vk.me/c633423/v633423092/2745e/NZtBthrAF9k.jpg") no-repeat center center fixed;
    -webkit-background-size: cover;
    -moz-background-size: cover;
    -o-background-size: cover;
    background-size: cover;
  }
  .padding {
    padding: 5px 10px 0 10px;
  }
  .screen {
    height: 100px;
  }
  .screen input {
    width: 100%;
    height: 100%;
    border: 0;
    background: transparent;
    text-align: right;
  }
  #history {
    font-size: 1.1rem;
    padding: 0 10px;
    letter-spacing: 5px;
  }
  #main {
    font-size: 3rem;
    color: #000;
    font-weight: 600;
    padding: 0 10px;
  }
  .history-screen {
    height: 30%;
  }
  .history-screen p{
    font-size: 15px;
    margin: 10px;
  }
  .main-screen {
    height: 70%;
  }
  .main-screen p {
    font-size: 30px;
    text-align: right;
    margin: 0 20px;
    overflow-x: hidden;
  }
  .top {
    display: flex;
    justify-content: space-between;
    align-items: stretch;
    line-height: 2rem;
  }
  .branding {
    flex-grow: 1;
    cursor: default;
    font-size: 0.8rem;
    padding-left: 15px;
  }
  .window {
    display: flex;
    justify-content: space-between;
    flex-grow: 1;
  }
  .window > div {
    flex-grow: 1;
    display: flex;
    align-items: center;
    justify-content: center;
    line-height: 2rem;
  }
  .container {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
  }
  #calculator {
    width: 300px;
    border: 1px solid #1883d7;
    box-shadow: 0 0 15px 2px rgba(255, 255, 255, 0.2);
    background: #f2f2f2;
  }
  .numbers{
    width: 60%;
    display: grid;
    grid-template-columns: repeat(3,1fr);
    grid-auto-rows: minmax(50px,auto);
  }
  .operators{
    width: 40%;
    display: grid;
    grid-template-columns: repeat(2,1fr);
    grid-auto-rows: minmax(50px,auto);
  }

  .row {
    display: flex;
    flex-wrap: wrap;
  }
  .button {
    line-height: 3.5rem;
    display: flex;
    justify-content: center;
    align-items: center;
  }
  .button.close:hover {
    background: #f00;
  }
  .sub-menu .button {
    line-height: 3rem;
  }
  .main-menu {
    background: #e6e6e6;
  }
  .number {
    font-weight: 900;
    font-size: 1.5rem;
  }
  .number:active {
    font-size: 1.4rem;
  }
  .button:hover, .button-top:hover {
    background: #cfcfcf;
    cursor: pointer;
  }
  .button:active {
    background: #b8b8b8;
  }
  .equals:hover {
    background: #1883d7;
  }
  .equals:active {
    background: rgb(67, 152, 207);
    background: rgba(67, 152, 207, 0.79);
  }
  .top .icon {
    width: 16px;
    height: 16px;
  }
  .icon {
    width: 25px;
    height: 25px;
  }
  .type {
    display: flex;
  }
  .column {
    display: flex;
    align-items: center;
  }
  .history {
    flex-grow: 6;
    justify-content: flex-end;
  }
  .button-top {
    display: flex;
    padding: 10px 15px;
    pointer-events: none;
  }
  .menu {
    flex-grow: 1;
    display: flex;
    justify-content: flex-start;
    align-items: center;
  }
  .image:active img {
    width: 24px;
    height: 24px;
  }
  .sign:active {
    font-size: 0.9rem;
  }
  .dot {
    font-weight: 900;
    font-size: 1.5rem;
  }
  .dot:active {
    font-size: 1.4rem;
  }
  .calculator-menu:hover {
    background: #cfcfcf;
    cursor: pointer;
  }
  .calculator-chosen {
    font-size: 1rem;
    letter-spacing: 2px;
    cursor: default;
    padding: 10px 12px;
    font-weight: 900;
  }
  .memory {
    display: flex;
    font-size: 0.75rem;
    color: #757575;
  }
  .memory > div:hover {
    color: #000;
    background: #cfcfcf;
    cursor: pointer;
  }
  .memory > div {
    flex-grow: 1;
    text-align: center;
    line-height: 2rem;
    pointer-events:none;
  }
  #plus-minus {
    pointer-events: none;
  }

  @media only screen and (max-width: 500px){
    .numbers,.operators{
      width: 100%;
      grid-template-columns: repeat(2,1fr);
    }
  }

</style>
