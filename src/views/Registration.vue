<template>
  <div class="sign">
    <img
      class="sign__background-image"
      src="@/assets/images/registration_background.jpg"
      alt="background"
    />
    <RegisterForm />
  </div>
</template>

<script>
import RegisterForm from "@/components/RegisterForm";

export default {
  components: { RegisterForm }
};
</script>
