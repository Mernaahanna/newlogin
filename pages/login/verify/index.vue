<template>
  <section class="level has-page-height" >
    <div class="level-item">
      <div class="container">
        <Verification />
      </div>
    </div>
  </section>
</template>

<script>
import Verification from "~/components/login/verify";
import 'bulma-helpers/css/bulma-helpers.min.css' 

export default {
  components: {
    Verification
  }
};
</script>
