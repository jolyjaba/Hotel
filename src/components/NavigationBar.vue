<template>
  <div class="navigation-bar__wrapper">
    <div class="navigation-bar">
      <div class="navigation-bar__left-side">
        <div class="logo">
          <img class="icon" src="../assets/svg/logo.svg" alt="logo" />
          <img class="text" src="../assets/svg/logo_text.svg" alt="logo_text" />
        </div>
      </div>
      <div class="navigation-bar__right-side">
        <div class="navigation-bar__group">
          <div class="link">
            <p>О нас</p>
          </div>
          <div class="link link--drop-down">
            <p>Услуги</p>
            <div class="drop-down">
              <img src="../assets/svg/dropDown.svg" alt="dropdown" />
            </div>
          </div>
          <div class="link"><p>Вакансии</p></div>
          <div class="link"><p>Новости</p></div>
          <div class="link link--drop-down">
            <p>Соглашения</p>
            <div class="drop-down">
              <img src="../assets/svg/dropDown.svg" alt="dropdown" />
            </div>
          </div>
        </div>
        <div class="button button--outlined">
          <p>войти</p>
        </div>
        <div class="button button--filled">
          <p>зарегистрироваться</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style lang="scss">
@import "./Fonts_Colors";

.logo {
  display: flex;
  .icon {
    margin-right: 12.5px;
  }
}

.link {
  p {
    color: $darkShade;
    opacity: 0.5;
  }
  &--drop-down {
    display: flex;
    .drop-down {
      width: 24px;
    }
  }
  &:not(:last-of-type) {
    margin-right: 20px;
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
    margin: 0 20px;
  }
}

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
</style>
