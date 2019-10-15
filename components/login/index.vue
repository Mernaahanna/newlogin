<template>
  <div class="columns is-centered">
    <div class="column is-5-tablet is-4-desktop is-3-widescreen">
      <div class="box">
        <div class="title is-2">
          <p>
            <strong>Welcome</strong>
            <br />
          </p>
        </div>
        <!-- message forget -->
        <article class="message is-warning is-small" v-if="forget==true">
          <div class="message-body">
            <p>Typo?</p>
            <p>
              Or did you
              <a href="/login/forget-credential">forget your credentials?</a>
            </p>
          </div>
        </article>
        <!-- username -->
        <div class="field">
          <label class="control">Username</label>
          <div class="control" v-if="form.email.length == 0">
            <input class="input" type="text" v-model="form.email" />
          </div>
          <!-- success -->
          <div class="control has-icons-right" v-else-if="form.email == 'sss@sss.sss'">
            <input
              class="input is-success"
              type="text"
              v-model="form.email"
              @change="forget = false"
            />
            <span class="icon is-small is-right">
              <font-awesome-icon :icon="['fas', 'check']" />
            </span>
          </div>
          <!-- danger -->
          <div class="control has-icons-right" v-else>
            <input class="input is-danger" type="text" v-model="form.email" />
            <span class="icon is-small is-right">
              <font-awesome-icon :icon="['fas', 'close']" />
            </span>
          </div>
        </div>
        <!-- password -->
        <div class="field">
          <label class="control">Password</label>
          <div class="control" v-if="form.password == 0">
            <input class="input" type="password" v-model="form.password" />
          </div>
          <!-- success -->
          <div class="control has-icons-right" v-else-if="form.password == '123456'">
            <input
              class="input is-success"
              type="password"
              v-model="form.password"
              @change="forget = false"
            />
            <span class="icon is-small is-right">
              <font-awesome-icon :icon="['fas', 'check']" />
            </span>
          </div>
          <!-- danger -->
          <div class="control has-icons-right" v-else>
            <input class="input is-danger" type="password" v-model="form.password" />
            <span class="icon is-small is-right">
              <font-awesome-icon :icon="['fas', 'close']" />
            </span>
          </div>
        </div>
        <!-- forget password -->
        <div class="content">
          <p>
            <a
              class="has-text-grey"
              href="/login/forget-credential"
            >I forget my username or password</a>
          </p>
        </div>
        <nav class="level">
          <div class="level-left"></div>
          <div class="level-right">
            <div class="level-item">
              <a class="button is-success is-rounded" @click="login">Login</a>
            </div>
          </div>
        </nav>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  name: "login",
  layout: "login",
  data() {
    return {
      form: {
        email: "",
        password: ""
      },
      forget: false
    };
  },
  methods: {
    login() {
      if (this.form.email == "sss@sss.sss" && this.form.password == "123456") {
        this.forget = false;
         this.$router.push('/backend')
      } else {
        this.forget = true;
      }
    }
  }
};
</script>