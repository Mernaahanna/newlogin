<template>
  <div class="box is-centered has-text-centered">
    <article class="media">
      <div class="media-content">
        <div class="content">
          <h3>What was your email again?</h3>
          <br />
          <p class="has-text-grey">
            We will send you a verification code to this email address with which
            you can create a new password.
          </p>
        </div>
        <!-- email -->
        <div class="field">
          <label class="control">Email</label>
          <div class="control">
            <input class="input" type="text" v-model="form.email" />
          </div>
        </div>
        <nav class="level">
          <div class="level-item">
            <a href="/login/verify" class="button is-info" style="margin-top:20%">Send verification code</a>
          </div>
        </nav>
      </div>
    </article>
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