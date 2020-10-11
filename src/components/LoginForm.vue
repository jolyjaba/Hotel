<template>
  <div class="form">
    <p class="form__title">Войти</p>
    <TextField type="email" placeHolder="Email" />
    <TextField type="password" placeHolder="Пароль" />
    <Button text="войти" type="filled directed" />
    <div class="form__footer">
      <p>Нет аккаунта на Toxin?</p>
      <Button
        @click="$router.push('/registration')"
        text="создать"
        type="outlined larger"
      />
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import TextField from "@/components/TextField.vue";
import Button from "@/components/Button.vue";

export default defineComponent({
  components: { TextField, Button }
});
</script>
