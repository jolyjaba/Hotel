<template>
  <NavigationBar />
  <router-view></router-view>
  <Footer />
</template>

<script lang="ts">
import { defineComponent } from "vue";
import NavigationBar from "@/layouts/NavigationBar.vue";
import Footer from "@/layouts/Footer.vue";

export default defineComponent({
  components: { NavigationBar, Footer }
});
</script>

<style lang="scss">
@import "@/components/Fonts_Colors";

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: $darkShade;
  @extend %Montserrat;
  font: {
    size: 14px;
    style: normal;
    weight: 400;
  }
  line-height: 24px;
  letter-spacing: 0em;
}

input {
  color: rgba(31, 32, 65, 0.75);
  border: 1px solid rgba(31, 32, 65, 0.25) {
    radius: 4px;
  }
  &:hover,
  &:focus {
    border-color: rgba(31, 32, 65, 0.5);
    &::placeholder {
      color: rgba(31, 32, 65, 0.75);
    }
  }
}

::placeholder {
  color: rgba(31, 32, 65, 0.25);
  @extend %Transition;
  @extend %Montserrat;
  font: {
    size: 14px;
    style: normal;
    weight: 400;
  }
  line-height: 24px;
  letter-spacing: 0em;
}

#app {
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  display: flex;
  flex-direction: column;
}

.form {
  position: absolute;
  background: #ffffff;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  padding: 40px 30px 30px;
  width: 380px;
  border: 1px solid rgba(0, 0, 0, 0.12);
  box-shadow: 0px 0px 25px rgba(0, 0, 0, 0.2);
  border-radius: 4px;
  display: flex;
  flex-direction: column;
  &__title {
    @extend %H1;
    color: $darkShade;
    text-align: left;
    margin-bottom: 15px;
  }
  &__sub-title {
    margin: 15px 0 0;
    @extend %H3;
    text-align: left;
    text-transform: uppercase;
    clear: both;
  }
  &__optional {
    display: flex;
    align-items: center;
    margin: 5px 0;
    label {
      cursor: pointer;
      color: $darkShade;
      opacity: 0.75;
    }
  }
  &__footer {
    margin-top: 30px;
    display: flex;
    align-items: center;
    justify-content: space-between;
  }
}

.sign {
  overflow: hidden;
  position: relative;
  height: 684px;
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
