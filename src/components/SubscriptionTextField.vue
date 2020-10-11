<template>
  <div class="field">
    <TextField type="email" placeholder="Email" />
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import TextField from "@/components/TextField.vue";

export default defineComponent({
  components: { TextField }
});
</script>

<style lang="scss" scoped>
.field {
  margin: 5px 0;
  margin-top: 20px;
  position: relative;
  &::before {
    content: "";
    cursor: pointer;
    z-index: 1;
    position: absolute;
    width: 44px;
    height: 44px;
    top: 0;
    right: 0;
    background: url("../assets/svg/arrow_forward_filled.svg") no-repeat center;
  }
  input {
    margin: 0;
  }
}
</style>
