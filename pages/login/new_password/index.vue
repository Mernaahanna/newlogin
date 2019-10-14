<template>
 <div class="container is-flex" style="min-height: 100vh; justify-content: center;">
    <div class="columns is-centered is-vcentered">
      <div class="column is-narrow has-text-centered is-full">
        <NewPass />
      </div>
    </div>
  </div>
</template>

<script>
import NewPass from "~/components/login/new_password";

export default {
  components: {
    NewPass
  }
};
</script>
