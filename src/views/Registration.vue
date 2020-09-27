<template>
  <div class="registration">
    <NavigationBar />
    <Main />
    <Footer />
  </div>
</template>

<script>
import NavigationBar from "../components/NavigationBar";
import Main from "../components/Main";
import Footer from "../components/Footer";

export default {
  components: { NavigationBar, Main, Footer }
};
</script>

<style lang="scss">
.registration {
  display: flex;
  flex-direction: column;
}
</style>
