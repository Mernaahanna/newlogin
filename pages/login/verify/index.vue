<template>
  <div class="container is-flex" style="min-height: 100vh; justify-content: center;">
    <div class="columns is-centered is-vcentered">
      <div class="column is-narrow has-text-centered is-four-fifths">
        <Verification />
      </div>
    </div>
  </div>
</template>

<script>
import Verification from "~/components/login/verify";

export default {
  components: {
    Verification
  }
};
</script>
