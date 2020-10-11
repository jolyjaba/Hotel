<template>
  <div class="form form--home">
    <p class="form__title">Найдём номера под ваши пожелания</p>
    <Dropdown type="date" :label="''" placeholder="ДД.ММ.ГГГГ" />
    <Dropdown type="default" :label="'гости'" placeholder="Сколько гостей" />
    <Button text="подобрать номер" type="filled directed" />
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import Dropdown from "@/components/Dropdown.vue";
import Button from "@/components/Button.vue";

export default defineComponent({
  components: { Dropdown, Button }
});
</script>

<style lang="scss" scoped>
.form {
  &--home {
    top: 70px;
    left: 20px;
    transform: translate(0, 0);
    @media (min-width: 1200px) {
      left: calc((100% - 1160px) / 2);
    }
  }
}
</style>
