<template>
  <div class="container-fluid">
    <div class="row">
      <div class="col-lg-5"></div>
      <div class="col-lg-3">
        <div class="row">
          <label for="display" style="color: white">__</label>
          <input type="numeric" name="display" disabled v-model="tempdisplay" />
        </div>
        <div class="row">
          <div class="col-lg-2">
            <button class="button btn btn-secondary" v-on:click="appendDisplay(7)">
              7
            </button>
          </div>
          <div class="col-lg-2">
            <button class="button btn btn-secondary" @click="appendDisplay(8)">
              8
            </button>
          </div>
          <div class="col-lg-2">
            <button class="button btn btn-secondary" @click="appendDisplay(9)">
              9
            </button>
          </div>
          <div class="col-lg-2">
            <button class="button btn btn-primary" @click="divide()">÷</button>
          </div>
        </div>
        <div class="row">
          <div class="col-lg-2">
            <button class="button btn btn-secondary" @click="appendDisplay(4)">
              4
            </button>
          </div>
          <div class="col-lg-2">
            <button class="button btn btn-secondary" @click="appendDisplay(5)">
              5
            </button>
          </div>
          <div class="col-lg-2">
            <button class="button btn btn-secondary" @click="appendDisplay(6)">
              6
            </button>
          </div>
          <div class="col-lg-2">
            <button class="button btn btn-primary" @click="multiply()">
              x
            </button>
          </div>
        </div>
        <div class="row">
          <div class="col-lg-2">
            <button class="button btn btn-secondary" @click="appendDisplay(1)">
              1
            </button>
          </div>
          <div class="col-lg-2">
            <button class="button btn btn-secondary" @click="appendDisplay(2)">
              2
            </button>
          </div>
          <div class="col-lg-2">
            <button class="button btn btn-secondary" @click="appendDisplay(3)">
              3
            </button>
          </div>
          <div class="col-lg-2">
            <button class="button btn btn-primary" @click="subtract()">
              -
            </button>
          </div>
        </div>
        <div class="row">
          <div class="col-lg-2">
            <button class="button btn btn-secondary" @click="appendDisplay(0)">
              0
            </button>
          </div>
          <div class="col-lg-2">
            <button class="button btn btn-secondary" @click="addDecimal()">
              .
            </button>
          </div>
          <div class="col-lg-2">
            <button class="button btn btn-warning" @click="operation()">
              =
            </button>
          </div>
          <div class="col-lg-2">
            <button class="button btn btn-primary" @click="add()">+</button>
          </div>
        </div>
        <div class="row">
          <button class="btn btn-warning" @click="wipe()">CLEAR</button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      display: "",
      tempdisplay: "",
      memory: "",
      operator: "",
      calcdisplay: "",
      clacmemory: "",
      decimal: false,
      clear: false,
    };
  },
  methods: {
    appendDisplay(value) {
      if (this.clear === true) {
        this.display = "";
        this.tempdisplay = "";
      }
      this.display += value;
      this.tempdisplay = this.display;
    },
    add() {
      this.clear = false;
      if (this.operator !== "") {
        this.tempdisplay = this.display;
        this.operation();
        this.operator = "add";
      } else {
        this.operator = "add";
      }
      this.memory = this.display;
      this.display = "";
      this.decimal = false;
    },
    subtract() {
      this.clear = false;
      if (this.operator !== "") {
        this.tempdisplay = this.display;
        this.operation();
        this.operator = "subtract";
      } else {
        this.operator = "subtract";
      }
      this.memory = this.display;
      this.display = "";
      this.decimal = false;
    },
    divide() {
      this.clear = false;
      if (this.operator !== "") {
        this.tempdisplay = this.display;
        this.operation();
        this.operator = "divide";
      } else {
        this.operator = "divide";
      }
      this.memory = this.display;
      this.display = "";
      this.decimal = false;
    },
    multiply() {
      this.clear = false;
      if (this.operator !== "") {
        this.tempdisplay = this.display;
        this.operation();
        this.operator = "multiply";
      } else {
        this.operator = "multiply";
      }
      this.memory = this.display;
      this.display = "";
      this.decimal = false;
    },
    operation() {
      this.calcdisplay = Number(this.display);
      this.calcmemory = Number(this.memory);
      if (this.operator === "add") {
        this.display = String(this.calcdisplay + this.calcmemory);
      } else {
        if (this.operator === "subtract") {
          this.display = String(this.calcmemory - this.calcdisplay);
        } else {
          if (this.operator === "multiply") {
            this.display = String(this.calcdisplay * this.calcmemory);
          } else {
            if (this.operator === "divide") {
              this.display = String(this.calcmemory / this.calcdisplay);
            }
          }
        }
      }
      this.tempdisplay = this.display;
      this.operator = "";
      this.memory = "";
      this.calcdisplay = "";
      this.calcmemory = "";
      this.clear = true;
    },
    addDecimal() {
      if (this.clear !== true) {
        if (this.decimal === false) {
          this.display += ".";
          this.decimal = true;
        }
      }
      this.tempdisplay = this.display;
    },
    wipe() {
      this.display = "";
      this.tempdisplay = "";
      this.memory = "";
      this.operator = "";
      this.calcdisplay = "";
      this.clacmemory = "";
      this.decimal = false;
      this.clear = false;
    },
  },
};
</script>

<style>
.button {
  border: none;
  padding: 15px 15px;
  width: 50px;
  text-align: center;
  text-decoration: none;
  display: inline-block;
  font-size: 16px;
  margin: 4px 2px;
  cursor: pointer;
}
</style>
