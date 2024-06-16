<template>
  <signupSuccessful />
</template>

<script>
import forgotPassword from "./forgotPassword.vue";
import confirmation from "./confirmation.vue";
import resetPassword from "./resetPassword.vue";
import signupSuccessful from "./signupSuccessful";

export default {
  components: {
    forgotPassword,
    confirmation,
    resetPassword,
    signupSuccessful
  },
};
</script>

<style scoped></style>
