<template>
  <div class="columns is-centered">
    <div class="column is-5-tablet is-4-desktop is-3-widescreen">
      <div class="box">
        <div class="content has-text-left">
          <h3>What was your email again?</h3>
          <br />
          <p class="has-text-grey">
            We will send you a verification code to this email address with which
            you can create a new password.
          </p>
        </div>
        <!-- email -->
        <div class="field has-text-left">
          <label class="control">Email</label>
          <div class="control">
            <input class="input" type="text" v-model="form.email" />
          </div>
        </div>
        <div class="has-text-centered">
          <a href="/login/verify" class="button is-info has-margin-top-40">Send verification code</a>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      form: {
        email: ""
      }
    };
  }
};
</script>