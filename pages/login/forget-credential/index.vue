<template>
  <div class="container is-flex" style="min-height: 100vh; justify-content: center;">
    <div class="columns is-centered is-vcentered">
      <div class="column is-narrow has-text-centered is-half">
        <Forget />
      </div>
    </div>
  </div>
</template>

<script>
import Forget from "~/components/login/forget-credential";

export default {
  components: {
    Forget
  }
};
</script>
