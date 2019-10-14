<template>
  <section class="level has-page-height" >
    <div class="level-item">
      <div class="container">
        <Forget />
      </div>
    </div>
  </section>
</template>

<script>
import Forget from "~/components/login/forget-credential";
import 'bulma-helpers/css/bulma-helpers.min.css' 

export default {
  components: {
    Forget
  }
};
</script>
