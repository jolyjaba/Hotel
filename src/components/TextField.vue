<template>
  <input class="text-field" />
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({});
</script>

<style lang="scss" scoped>
@import "@/components/Fonts_Colors";

.text-field {
  width: 100%;
  height: 44px;
  padding: 13px 15px;
  margin: 5px 0;
  outline: none;
  white-space: nowrap;
  overflow: hidden;
  text-overflow: ellipsis;
}
</style>
