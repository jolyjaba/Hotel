<template>
  <div class="main">
    <img
      class="main__background-image"
      src="../assets/images/background.png"
      alt="background"
    />
    <Form />
  </div>
</template>

<script>
import Form from "./Form";

export default {
  components: { Form }
};
</script>

<style lang="scss">
.main {
  overflow: hidden;
  position: relative;
  height: 684px;
  &__background-image {
    display: block;
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    height: 100vh;
  }
}
</style>
