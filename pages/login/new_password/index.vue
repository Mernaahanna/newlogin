<template>
 <section class="level has-page-height" >
    <div class="level-item">
      <div class="container">
        <NewPass />
      </div>
    </div>
  </section>
</template>

<script>
import NewPass from "~/components/login/new_password";
import 'bulma-helpers/css/bulma-helpers.min.css' 

export default {
  components: {
    NewPass
  }
};
</script>
