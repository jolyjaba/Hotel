<template>
  <div class="sign">
    <img
      class="sign__background-image"
      src="@/assets/images/registration_background.jpg"
      alt="background"
    />
    <LoginForm />
  </div>
</template>

<script>
import LoginForm from "@/components/LoginForm";

export default {
  components: { LoginForm }
};
</script>
