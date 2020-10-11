<template>
  <div class="home">
    <img
      class="home__background-image"
      src="@/assets/images/home_background.jpg"
      alt="background"
    />
    <FindRoomForm />
  </div>
</template>

<script>
import FindRoomForm from "@/components/FindRoomForm";

export default {
  components: { FindRoomForm }
};
</script>

<style lang="scss">
.home {
  height: 830px;
  width: 100%;
  overflow: hidden;
  position: relative;
  &__background-image {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    pointer-events: none;
    @media (min-width: 1440px) {
      width: 100%;
    }
  }
}
</style>
