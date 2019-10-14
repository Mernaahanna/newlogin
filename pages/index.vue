<template>
  <section class="level has-page-height" >
    <div class="level-item">
      <div class="container">
        <Login />
      </div>
    </div>
  </section>
</template>

<script>
import Login from "~/components/login";
import 'bulma-helpers/css/bulma-helpers.min.css' 

export default {
  components: {
    Login
  }
};
</script>
