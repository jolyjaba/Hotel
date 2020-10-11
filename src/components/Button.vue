<template>
  <div class="button" :class="`button--${type}`">
    <p>{{ text }}</p>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  props: {
    text: { type: String, required: true },
    type: { type: String, required: true }
  }
});
</script>

<style lang="scss" scoped>
@import "@/components/Fonts_Colors";

.button {
  padding: 7px 18px;
  &:not(:last-of-type) {
    margin-right: 20px;
  }
  p {
    @extend %H3;
    text-transform: uppercase;
  }
  &--outlined {
    width: 87px;
    background: #fff;
    color: $purple;
  }
  &--filled {
    width: 196px;
    color: #fff;
  }
  &--filled,
  &--outlined {
    height: 34px;
    position: relative;
    $border: 2px;
    background-clip: padding-box;
    border: solid $border transparent {
      radius: 2em;
    }
    @extend %Transition;
    &:active {
      &::before {
        opacity: 0.5;
      }
    }
    &::before {
      content: "";
      position: absolute;
      top: 0;
      right: 0;
      bottom: 0;
      left: 0;
      z-index: -1;
      margin: -$border;
      border-radius: inherit;
      background: linear-gradient(180deg, #bc9cff 0%, #8ba4f9 100%);
    }
  }
}

.larger {
  padding: 12px;
  height: 44px;
  width: 99px;
}

.directed {
  width: 100%;
  height: 44px;
  margin-top: 15px;
  padding: 12px;
  &::after {
    content: "";
    background: url("../assets/svg/arrow_forward.svg") no-repeat center;
    position: absolute;
    width: 44px;
    height: 44px;
    right: -2px;
    top: -2px;
  }
  &:not(:last-of-type) {
    margin-right: 0px;
  }
}
</style>
