<template>
 <div class="columns is-centered">
    <div class="column is-5-tablet is-4-desktop is-3-widescreen">
      <div class="box">
        <div class="content">
          <h3>Hi , Username</h3>
          <br />
          <p class="has-text-grey">Wow, great username!</p>
        </div>
        <!-- lock -->
        <div>
          <style>
            :root {
              --top: {{ Top+ '%'}};
              --bg-color: {{ Color }}
            }
          </style>
          <div class="padlock">
            <div class="keyhole checkmark" v-show="success"></div>
          </div>
        </div>
        <!-- password -->
        <div class="field">
          <label class="control">New Password</label>
          <div class="control">
            <input
              :class="form.password.length >5? 'input is-success' : 'input'"
              type="password"
              v-model="form.password"
              @input="checkExist($event)"
            />
          </div>
        </div>
        <!-- repeat password -->
        <div class="field">
          <label class="control">Repeat Password</label>
          <div class="control has-icons-right" v-if="form.re_password.length == 0">
            <input class="input" type="password" v-model="form.re_password" />
          </div>
          <div
            class="control has-icons-right"
            v-else-if="form.password===form.re_password && form.password.length!=0"
          >
            <input class="input is-success" type="password" v-model="form.re_password" />
            <span class="icon is-small is-right">
              <font-awesome-icon :icon="['fas', 'check']" />
            </span>
          </div>
          <div class="control has-icons-right" v-else>
            <input class="input is-danger" type="password" v-model="form.re_password" />
            <span class="icon is-small is-right">
              <font-awesome-icon :icon="['fas', 'close']" />
            </span>
          </div>
        </div>
          <div class="has-margin-top-30 has-text-centered">
            <a href="/" class="button is-success">Save</a>
          </div>
      </div>
    </div>
  </div>
</template>
<script>
import Vue from "vue";
import CircularCountDownTimer from "vue-circular-count-down-timer";
Vue.use(CircularCountDownTimer);
export default {
  data() {
    return {
      form: {
        re_password: "",
        password: ""
      },
      Top: -73,
      Color: "red",
      success: false
    };
  },
  methods: {
    checkExist(event) {
      // change status of padlock according to length of password
      if (event.target.value.length <= 5 && event.target.value.length != 0) {
        let count = event.target.value.length;
        let newtop = -73;
        this.success = false;
        this.Top = newtop + 3 * count;
        this.Color = "rgb(236, 187, 141)";
      } else if (event.target.value.length === 0) {
        this.Top = -73;
        this.Color = "red";
        this.success = false;
      } else {
        this.Top = this.Top;
        this.Color = "rgb(125, 223, 166)";
        this.success = true;
      }
    }
  }
};
</script>
<style scoped>
.padlock {
  position: relative;
  width: 91px;
  height: 70px;
  background-image: linear-gradient(
    to bottom right,
    var(--bg-color) 30%,
    var(--bg-color) 8%
  );
  border-radius: 16px 20px 20px 20px;
  cursor: pointer;
  margin-top: 27% !important;
  margin-left: 30%;
  margin-bottom: 10%;
}
.padlock::before {
  content: "";
  position: absolute;
  left: 12%;
  color: var(--bg-color);
  top: var(--top);
  width: 63px;
  height: 79px;
  border-radius: 38px;
  border: 13px solid var(--bg-color);
  clip-path: polygon(
    0% 0%,
    100% 0%,
    100% 65%,
    50% 65%,
    50% 57%,
    22% 57%,
    22% 51%,
    15% 51%,
    14% 52%,
    14% 53%,
    15% 54%,
    22% 54%,
    18% 57%,
    2% 57%,
    0% 55%
  );
}
.checkmark {
  display: inline-block;
  content: "";
  display: block;
  width: 10px;
  height: 25px;
  border: solid green;
  border-width: 0 4px 4px 0;
  transform: rotate(45deg);
}
.keyhole {
  position: absolute;
  top: 25%;
  left: 45%;
}
</style>