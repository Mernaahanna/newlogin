<template>
  <div class="columns is-centered">
    <div class="column is-5-tablet is-4-desktop is-3-widescreen">
      <div class="box">
        <div class="content">
          <h3>We send the code to your email</h3>
          <br />
          <p class="has-text-grey">Please fill it in below.</p>
        </div>
        <!-- verification input number -->
        <div class="field">
          <label class="control">Verification code</label>
          <div class="columns" @click="nextInput()">
            <div class="column">
              <input
                class="input"
                id="a"
                required
                type="text"
                maxlength="1"
                :size="1"
                pattern="[0-9]{1}"
              />
            </div>
            <div class="column">
              <input
                class="input"
                id="b"
                type="text"
                maxlength="1"
                size="1"
                min="0"
                max="9"
                pattern="[0-9]{1}"
              />
            </div>
            <div class="column">
              <input
                class="input"
                id="c"
                max="9"
                min="1"
                maxlength="1"
                size="1"
                required
                type="text"
                pattern="[0-9]{1}"
              />
            </div>
            <div class="column">
              <input
                class="input"
                id="d"
                max="9"
                min="1"
                maxlength="1"
                size="1"
                required
                type="text"
                pattern="[0-9]{1}"
              />
            </div>
          </div>
        </div>
        <!-- timer -->
        <div class="has-text-centered has-margin-top-30">
          <circular-count-down-timer :initial-value="60" :steps="60" :size="100" :second-label="''"></circular-count-down-timer>
        </div>
        <div class="has-text-centered has-margin-top-10">
          <a href="/login/new_password" class="button is-success">Verify</a>
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
        email: ""
      }
    };
  },
  methods: {
    nextInput() {
      // focus in the next input
      var a = document.getElementById("a"),
        b = document.getElementById("b"),
        c = document.getElementById("c"),
        d = document.getElementById("d");

      a.onkeyup = function() {
        if (
          this.value.length === parseInt(this.attributes["maxlength"].value)
        ) {
          b.focus();
        }
      };

      b.onkeyup = function() {
        if (
          this.value.length === parseInt(this.attributes["maxlength"].value)
        ) {
          c.focus();
        }
      };
      c.onkeyup = function() {
        if (
          this.value.length === parseInt(this.attributes["maxlength"].value)
        ) {
          d.focus();
        }
      };
    }
  }
};
</script>