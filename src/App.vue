<template>
  <Registration />
</template>

<script>
import Registration from "./views/Registration";

export default {
  components: { Registration }
};
</script>

<style lang="scss">
@import "./components/Fonts_Colors";

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body,
::placeholder {
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

title {
  display: block;
}

#app {
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
}
</style>
