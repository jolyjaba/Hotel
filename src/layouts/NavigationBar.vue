<template>
  <div class="navigation-bar__wrapper">
    <div class="navigation-bar">
      <div class="navigation-bar__left-side">
        <div @click="$router.push('/')" class="logo">
          <img class="icon" src="@/assets/svg/logo.svg" alt="logo" />
          <img class="text" src="@/assets/svg/logo_text.svg" alt="logo_text" />
        </div>
      </div>
      <div class="navigation-bar__right-side">
        <div class="navigation-bar__group">
          <div class="link active">
            <p>О нас</p>
          </div>
          <div class="link link--drop-down">
            <p>Услуги</p>
            <div class="drop-down">
              <img src="@/assets/svg/dropDown.svg" alt="dropdown" />
            </div>
          </div>
          <div class="link"><p>Вакансии</p></div>
          <div class="link"><p>Новости</p></div>
          <div class="link link--drop-down">
            <p>Соглашения</p>
            <div class="drop-down">
              <img src="@/assets/svg/dropDown.svg" alt="dropdown" />
            </div>
          </div>
        </div>
        <Button @click="$router.push('/login')" text="войти" type="outlined" />
        <Button
          @click="$router.push('/registration')"
          text="зарегистрироваться"
          type="filled"
        />
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import Button from "@/components/Button.vue";

export default defineComponent({
  components: { Button }
});
</script>

<style lang="scss">
@import "@/components/Fonts_Colors";

.logo,
.link > p,
.button,
.drop-down > img {
  cursor: pointer;
}

.logo {
  display: flex;
  .icon {
    margin-right: 12.5px;
  }
}

.link {
  &.active {
    p {
      font-weight: 700;
      opacity: 0.75;
    }
  }
  p {
    transition: opacity 0.1s cubic-bezier(0.55, 0.085, 0.68, 0.53);
    color: $darkShade;
    opacity: 0.5;
    &:hover {
      opacity: 0.75;
    }
  }
  &--drop-down {
    display: flex;
    .drop-down {
      width: 24px;
      img {
        pointer-events: none;
      }
    }
  }
}

.navigation-bar {
  max-width: 1200px;
  min-height: 70px;
  margin: auto;
  padding: 0 15px;
  display: flex;
  align-items: center;
  justify-content: space-between;
  &__wrapper {
    box-shadow: 0px 10px 20px rgba(31, 32, 65, 0.05);
    z-index: 1;
  }
  &__left-side,
  &__right-side {
    display: flex;
    align-items: center;
    margin: 0 5px;
  }
  &__group {
    display: flex;
    justify-content: space-between;
    width: 446px;
    margin: 0 20px;
  }
}
</style>
