<template>
  <div class="surprise">
    <div class="container-fluid">
      <div>
        <button @click="start()">Start</button>
      </div>
      <div>
        Score: {{ score }}
        <br />
        Time left: {{ time }}
        <br />
        Combo: {{ combo }} x
        <br />
        Dots will change from red to green. Click on the dots when they are green
        for the most points.
      </div>
      <div class="row">
        <div class="col-lg-2"></div>
        <div class="col-lg-8">
          <div class="row">
            <div class="col-lg-2">
              <span v-bind:class="testClass(states[0][0])" @click="testFunction(states[0][0], 0, 0)"></span>
              <!-- <span
                class="dotgrey"
                v-if="states[0][0] == 1"
                @click="fail()"
              ></span>
              <span
                class="dotred"
                v-if="states[0][0] == 2"
                @click="green(0, 0)"
              ></span>
              <span
                class="dotgreen"
                v-if="states[0][0] == 3"
                @click="red(0, 0)"
              ></span> -->
            </div>
            <div class="col-lg-2">
              <span v-bind:class="testClass(states[0][1])" @click="testFunction(states[0][1], 0, 1)"></span>
              <!-- <span
                class="dotgrey"
                v-if="states[0][1] == 1"
                @click="fail()"
              ></span>
              <span
                class="dotred"
                v-if="states[0][1] == 2"
                @click="green(0, 1)"
              ></span>
              <span
                class="dotgreen"
                v-if="states[0][1] == 3"
                @click="red(0, 1)"
              ></span> -->
            </div>
            <div class="col-lg-2">
              <span
                class="dotgrey"
                v-if="states[0][2] == 1"
                @click="fail()"
              ></span>
              <span
                class="dotred"
                v-if="states[0][2] == 2"
                @click="green(0, 2)"
              ></span>
              <span
                class="dotgreen"
                v-if="states[0][2] == 3"
                @click="red(0, 2)"
              ></span>
            </div>
            <div class="col-lg-2">
              <span
                class="dotgrey"
                v-if="states[0][3] == 1"
                @click="fail()"
              ></span>
              <span
                class="dotred"
                v-if="states[0][3] == 2"
                @click="green(0, 3)"
              ></span>
              <span
                class="dotgreen"
                v-if="states[0][3] == 3"
                @click="red(0, 3)"
              ></span>
            </div>
            <div class="col-lg-2">
              <span
                class="dotgrey"
                v-if="states[0][4] == 1"
                @click="fail()"
              ></span>
              <span
                class="dotred"
                v-if="states[0][4] == 2"
                @click="green(0, 4)"
              ></span>
              <span
                class="dotgreen"
                v-if="states[0][4] == 3"
                @click="red(0, 4)"
              ></span>
            </div>
            <div class="col-lg-2">
              <span
                class="dotgrey"
                v-if="states[0][5] == 1"
                @click="fail()"
              ></span>
              <span
                class="dotred"
                v-if="states[0][5] == 2"
                @click="green(0, 5)"
              ></span>
              <span
                class="dotgreen"
                v-if="states[0][5] == 3"
                @click="red(0, 5)"
              ></span>
            </div>
          </div>
          <br />
          <div class="row">
            <div class="col-lg-2">
              <span
                class="dotgrey"
                v-if="states[1][0] == 1"
                @click="fail()"
              ></span>
              <span
                class="dotred"
                v-if="states[1][0] == 2"
                @click="green(1, 0)"
              ></span>
              <span
                class="dotgreen"
                v-if="states[1][0] == 3"
                @click="red(1, 0)"
              ></span>
            </div>
            <div class="col-lg-2">
              <span
                class="dotgrey"
                v-if="states[1][1] == 1"
                @click="fail()"
              ></span>
              <span
                class="dotred"
                v-if="states[1][1] == 2"
                @click="green(1, 1)"
              ></span>
              <span
                class="dotgreen"
                v-if="states[1][1] == 3"
                @click="red(1, 1)"
              ></span>
            </div>
            <div class="col-lg-2">
              <span
                class="dotgrey"
                v-if="states[1][2] == 1"
                @click="fail()"
              ></span>
              <span
                class="dotred"
                v-if="states[1][2] == 2"
                @click="green(1, 2)"
              ></span>
              <span
                class="dotgreen"
                v-if="states[1][2] == 3"
                @click="red(1, 2)"
              ></span>
            </div>
            <div class="col-lg-2">
              <span
                class="dotgrey"
                v-if="states[1][3] == 1"
                @click="fail()"
              ></span>
              <span
                class="dotred"
                v-if="states[1][3] == 2"
                @click="green(1, 3)"
              ></span>
              <span
                class="dotgreen"
                v-if="states[1][3] == 3"
                @click="red(1, 3)"
              ></span>
            </div>
            <div class="col-lg-2">
              <span
                class="dotgrey"
                v-if="states[1][4] == 1"
                @click="fail()"
              ></span>
              <span
                class="dotred"
                v-if="states[1][4] == 2"
                @click="green(1, 4)"
              ></span>
              <span
                class="dotgreen"
                v-if="states[1][4] == 3"
                @click="red(1, 4)"
              ></span>
            </div>
            <div class="col-lg-2">
              <span
                class="dotgrey"
                v-if="states[1][5] == 1"
                @click="fail()"
              ></span>
              <span
                class="dotred"
                v-if="states[1][5] == 2"
                @click="green(1, 5)"
              ></span>
              <span
                class="dotgreen"
                v-if="states[1][5] == 3"
                @click="red(1, 5)"
              ></span>
            </div>
          </div>
          <br />
          <div class="row">
            <div class="col-lg-2">
              <span
                class="dotgrey"
                v-if="states[2][0] == 1"
                @click="fail()"
              ></span>
              <span
                class="dotred"
                v-if="states[2][0] == 2"
                @click="green(2, 0)"
              ></span>
              <span
                class="dotgreen"
                v-if="states[2][0] == 3"
                @click="red(2, 0)"
              ></span>
            </div>
            <div class="col-lg-2">
              <span
                class="dotgrey"
                v-if="states[2][1] == 1"
                @click="fail()"
              ></span>
              <span
                class="dotred"
                v-if="states[2][1] == 2"
                @click="green(2, 1)"
              ></span>
              <span
                class="dotgreen"
                v-if="states[2][1] == 3"
                @click="red(2, 1)"
              ></span>
            </div>
            <div class="col-lg-2">
              <span
                class="dotgrey"
                v-if="states[2][2] == 1"
                @click="fail()"
              ></span>
              <span
                class="dotred"
                v-if="states[2][2] == 2"
                @click="green(2, 2)"
              ></span>
              <span
                class="dotgreen"
                v-if="states[2][2] == 3"
                @click="red(2, 2)"
              ></span>
            </div>
            <div class="col-lg-2">
              <span
                class="dotgrey"
                v-if="states[2][3] == 1"
                @click="fail()"
              ></span>
              <span
                class="dotred"
                v-if="states[2][3] == 2"
                @click="green(2, 3)"
              ></span>
              <span
                class="dotgreen"
                v-if="states[2][3] == 3"
                @click="red(2, 3)"
              ></span>
            </div>
            <div class="col-lg-2">
              <span
                class="dotgrey"
                v-if="states[2][4] == 1"
                @click="fail()"
              ></span>
              <span
                class="dotred"
                v-if="states[2][4] == 2"
                @click="green(2, 4)"
              ></span>
              <span
                class="dotgreen"
                v-if="states[2][4] == 3"
                @click="red(2, 4)"
              ></span>
            </div>
            <div class="col-lg-2">
              <span
                class="dotgrey"
                v-if="states[2][5] == 1"
                @click="fail()"
              ></span>
              <span
                class="dotred"
                v-if="states[2][5] == 2"
                @click="green(2, 5)"
              ></span>
              <span
                class="dotgreen"
                v-if="states[2][5] == 3"
                @click="red(2, 5)"
              ></span>
            </div>
          </div>
          <br />
          <div class="row">
            <div class="col-lg-2">
              <span
                class="dotgrey"
                v-if="states[3][0] == 1"
                @click="fail()"
              ></span>
              <span
                class="dotred"
                v-if="states[3][0] == 2"
                @click="green(3, 0)"
              ></span>
              <span
                class="dotgreen"
                v-if="states[3][0] == 3"
                @click="red(3, 0)"
              ></span>
            </div>
            <div class="col-lg-2">
              <span
                class="dotgrey"
                v-if="states[3][1] == 1"
                @click="fail()"
              ></span>
              <span
                class="dotred"
                v-if="states[3][1] == 2"
                @click="green(3, 1)"
              ></span>
              <span
                class="dotgreen"
                v-if="states[3][1] == 3"
                @click="red(3, 1)"
              ></span>
            </div>
            <div class="col-lg-2">
              <span
                class="dotgrey"
                v-if="states[3][2] == 1"
                @click="fail()"
              ></span>
              <span
                class="dotred"
                v-if="states[3][2] == 2"
                @click="green(3, 2)"
              ></span>
              <span
                class="dotgreen"
                v-if="states[3][2] == 3"
                @click="red(3, 2)"
              ></span>
            </div>
            <div class="col-lg-2">
              <span
                class="dotgrey"
                v-if="states[3][3] == 1"
                @click="fail()"
              ></span>
              <span
                class="dotred"
                v-if="states[3][3] == 2"
                @click="green(3, 3)"
              ></span>
              <span
                class="dotgreen"
                v-if="states[3][3] == 3"
                @click="red(3, 3)"
              ></span>
            </div>
            <div class="col-lg-2">
              <span
                class="dotgrey"
                v-if="states[3][4] == 1"
                @click="fail()"
              ></span>
              <span
                class="dotred"
                v-if="states[3][4] == 2"
                @click="green(3, 4)"
              ></span>
              <span
                class="dotgreen"
                v-if="states[3][4] == 3"
                @click="red(3, 4)"
              ></span>
            </div>
            <div class="col-lg-2">
              <span
                class="dotgrey"
                v-if="states[3][5] == 1"
                @click="fail()"
              ></span>
              <span
                class="dotred"
                v-if="states[3][5] == 2"
                @click="green(3, 5)"
              ></span>
              <span
                class="dotgreen"
                v-if="states[3][5] == 3"
                @click="red(3, 5)"
              ></span>
            </div>
          </div>
          <br />
          <div class="row">
            <div class="col-lg-2">
              <span
                class="dotgrey"
                v-if="states[4][0] == 1"
                @click="fail()"
              ></span>
              <span
                class="dotred"
                v-if="states[4][0] == 2"
                @click="green(4, 0)"
              ></span>
              <span
                class="dotgreen"
                v-if="states[4][0] == 3"
                @click="red(4, 0)"
              ></span>
            </div>
            <div class="col-lg-2">
              <span
                class="dotgrey"
                v-if="states[4][1] == 1"
                @click="fail()"
              ></span>
              <span
                class="dotred"
                v-if="states[4][1] == 2"
                @click="green(4, 1)"
              ></span>
              <span
                class="dotgreen"
                v-if="states[4][1] == 3"
                @click="red(4, 1)"
              ></span>
            </div>
            <div class="col-lg-2">
              <span
                class="dotgrey"
                v-if="states[4][2] == 1"
                @click="fail()"
              ></span>
              <span
                class="dotred"
                v-if="states[4][2] == 2"
                @click="green(4, 2)"
              ></span>
              <span
                class="dotgreen"
                v-if="states[4][2] == 3"
                @click="red(4, 2)"
              ></span>
            </div>
            <div class="col-lg-2">
              <span
                class="dotgrey"
                v-if="states[4][3] == 1"
                @click="fail()"
              ></span>
              <span
                class="dotred"
                v-if="states[4][3] == 2"
                @click="green(4, 3)"
              ></span>
              <span
                class="dotgreen"
                v-if="states[4][3] == 3"
                @click="red(4, 3)"
              ></span>
            </div>
            <div class="col-lg-2">
              <span
                class="dotgrey"
                v-if="states[4][4] == 1"
                @click="fail()"
              ></span>
              <span
                class="dotred"
                v-if="states[4][4] == 2"
                @click="green(4, 4)"
              ></span>
              <span
                class="dotgreen"
                v-if="states[4][4] == 3"
                @click="red(4, 4)"
              ></span>
            </div>
            <div class="col-lg-2">
              <span
                class="dotgrey"
                v-if="states[4][5] == 1"
                @click="fail()"
              ></span>
              <span
                class="dotred"
                v-if="states[4][5] == 2"
                @click="green(4, 5)"
              ></span>
              <span
                class="dotgreen"
                v-if="states[4][5] == 3"
                @click="red(4, 5)"
              ></span>
            </div>
          </div>
          <br />
          <div class="row">
            <div class="col-lg-2">
              <span
                class="dotgrey"
                v-if="states[5][0] == 1"
                @click="fail()"
              ></span>
              <span
                class="dotred"
                v-if="states[5][0] == 2"
                @click="green(5, 0)"
              ></span>
              <span
                class="dotgreen"
                v-if="states[5][0] == 3"
                @click="red(5, 0)"
              ></span>
            </div>
            <div class="col-lg-2">
              <span
                class="dotgrey"
                v-if="states[5][1] == 1"
                @click="fail()"
              ></span>
              <span
                class="dotred"
                v-if="states[5][1] == 2"
                @click="green(5, 1)"
              ></span>
              <span
                class="dotgreen"
                v-if="states[5][1] == 3"
                @click="red(5, 1)"
              ></span>
            </div>
            <div class="col-lg-2">
              <span
                class="dotgrey"
                v-if="states[5][2] == 1"
                @click="fail()"
              ></span>
              <span
                class="dotred"
                v-if="states[5][2] == 2"
                @click="green(5, 2)"
              ></span>
              <span
                class="dotgreen"
                v-if="states[5][2] == 3"
                @click="red(5, 2)"
              ></span>
            </div>
            <div class="col-lg-2">
              <span
                class="dotgrey"
                v-if="states[5][3] == 1"
                @click="fail()"
              ></span>
              <span
                class="dotred"
                v-if="states[5][3] == 2"
                @click="green(5, 3)"
              ></span>
              <span
                class="dotgreen"
                v-if="states[5][3] == 3"
                @click="red(5, 3)"
              ></span>
            </div>
            <div class="col-lg-2">
              <span
                class="dotgrey"
                v-if="states[5][4] == 1"
                @click="fail()"
              ></span>
              <span
                class="dotred"
                v-if="states[5][4] == 2"
                @click="green(5, 4)"
              ></span>
              <span
                class="dotgreen"
                v-if="states[5][4] == 3"
                @click="red(5, 4)"
              ></span>
            </div>
            <div class="col-lg-2">
              <span
                class="dotgrey"
                v-if="states[5][5] == 1"
                @click="fail()"
              ></span>
              <span
                class="dotred"
                v-if="states[5][5] == 2"
                @click="green(5, 5)"
              ></span>
              <span
                class="dotgreen"
                v-if="states[5][5] == 3"
                @click="red(5, 5)"
              ></span>
            </div>
          </div>
          <br />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import sound from "../assets/padowo_padowo.mp3";
export default {
  data() {
    return {
      score: 0,
      time: 0,
      started: false,
      counter: 0,
      combo: 1,
      placeholder: "",
      toClick: [
        [
          50, 49, 48, 47, 46, 45, 44, 43, 42, 41, 
          40, 39, 38, 37, 36, 35, 34, 33, 32, 31, 
          30, 29, 38, 27, 26, 25, 24, 23, 22, 21, 
          20, 19, 18, 17, 16, 15, 14, 13, 12, 11,
          10,  9,  8,  7,  6,  5,  4,  3,  2,  1,
        ], //time, ref
        [
          6, 6, 5, 2, 0, 4, 3, 5, 2, 0,
          1, 3, 2, 4, 3, 5, 3, 1, 0, 2,
          1, 3, 3, 0, 1, 2, 4, 1, 5, 3,
          5, 2, 4, 1, 4, 5, 3, 0, 5, 3,
          0, 5, 2, 6, 6, 6, 4, 2, 0, 6,
        ], //row
        [
          6, 6, 1, 5, 3, 4, 5, 1, 1, 5,
          0, 3, 5, 1, 1, 3, 5, 4, 3, 4,
          2, 2, 5, 2, 2, 0, 1, 5, 0, 3,
          0, 5, 3, 1, 2, 3, 1, 3, 2, 1,
          3, 3, 1, 6, 6, 6, 4, 3, 5, 6,
        ], //column
      ],
      states: [
        [1,1,1,1,1,1],
        [1,1,1,1,1,1],
        [1,1,1,1,1,1],
        [1,1,1,1,1,1],
        [1,1,1,1,1,1],
        [1,1,1,1,1,1],
        [6,6,6,6,6,6,6,6,6,6,6,6]
      ],
    };
  },
  methods: {
    start() {
      if (this.started == false) {
        this.time = 50;
        this.score = 0;
        this.combo = 1;
        this.started = true;
        this.counter = 0;
        this.placeholder = setInterval(() => {
          if (this.time == 47) {
            var audio = new Audio(sound);
            audio.play();
          }
          for (let i = 0; i < 6; i++) {
            for (let j = 0; j < 6; j++) {
              if (this.states[i][j] == 3) {
                this.states[i][j]--;
              }
              else {
                if (this.states[i][j] == 2){
                  this.states[i][j]--;
                  this.combo = 1
                }
              }
            }
          }
          this.states[this.toClick[1][this.counter]][this.toClick[2][this.counter]] = 3
          this.counter ++
          if (this.time !== 0) {
            this.time--;
          }
          if (this.time == 0){
            this.started = false;
            clearInterval(this.placeholder)
          }
        }, 1000);
      }
    },
    red(i, j) {
      this.score = this.score + this.combo * 100;
      this.combo++;
      this.states[i][j] = 1;
    },
    green(i, j) {
      this.score = this.score + this.combo * 300;
      this.combo++;
      this.states[i][j] = 1;
    },
    fail() {
      this.combo = 1;
    },
    testClass(value){
      if(value == 1){
        return "dotgrey"
      }
      else if(value == 2){
        return "dotred"
      }
      else if(value == 3){
        return "dotgreen"
      }
    },
    testFunction(value, i, j){
      if(value == 1){
        return this.fail()
      }
      else if(value == 2){
        return this.green(i,j)
      }
      else if(value == 3){
        return this.red(i,j)
      }
    }
  },
};
</script>

<style scoped>
.dotgrey {
  height: 75px;
  width: 75px;
  background-color: #bbb;
  border-radius: 50%;
  display: inline-block;
}
.dotred {
  height: 75px;
  width: 75px;
  background-color: green;
  border-radius: 50%;
  display: inline-block;
  color: green;
}
.dotgreen {
  height: 75px;
  width: 75px;
  background-color: red;
  border-radius: 50%;
  display: inline-block;
  color: red;
}
/* if youre wondering about why the styles are reversed, its bc i fucked up earlier and im too lazy to change 72 values to the opposite color. i started it but it took too long so im just fixing the name and the score values and thats it. sry for confusion */
</style>