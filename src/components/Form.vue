<template>
  <div class="form">
    <title class="form__title">Регистрация аккаунта</title>
    <input type="text" class="form__name" placeholder="Имя" />
    <input type="text" class="form__surname" placeholder="Фамилия" />
    <div class="options">
      <div class="option">
        <div class="radio-button">
          <input type="radio" name="gender" id="man" value="man" />
          <label for="man">
            <div class="radio-button__border">
              <div class="radio-button__dot"></div>
            </div>
          </label>
          <label for="man">Мужчина</label>
        </div>
      </div>
      <div class="option">
        <div class="radio-button">
          <input type="radio" name="gender" id="woman" value="woman" />
          <label for="woman">
            <div class="radio-button__border">
              <div class="radio-button__dot"></div>
            </div>
          </label>
          <label for="woman">Женщина</label>
        </div>
      </div>
    </div>
    <title class="form__sub-title">дата рождения</title>
    <input type="text" class="form__birth" placeholder="ДД.ММ.ГГГГ" />
    <title class="form__sub-title">данные для входа в сервис</title>
    <input type="email" class="form__email" placeholder="Email" />
    <input type="password" class="form__password" placeholder="Пароль" />
    <div class="form__optional">
      <div class="toggle">
        <input type="checkbox" name="toggle" id="toggle" />
        <label for="toggle">
          <div class="toggle__border">
            <div class="toggle__button"></div>
          </div>
        </label>
      </div>
      <label for="toggle">Получать спецпредложения</label>
    </div>
    <div class="button button--filled button--filled-pay">
      <p>перейти к оплате</p>
    </div>
    <div class="form__sign-in">
      <p>Уже есть аккаунт на Toxin</p>
      <div class="button button--outlined button--outlined-sign-in">
        <p>войти</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style lang="scss">
@import "./Fonts_Colors";

.button {
  &--outlined {
    &-sign-in {
      padding: 12px;
      height: 44px;
      width: 99px;
    }
  }
  &--filled {
    &-pay {
      width: 320px;
      height: 44px;
      margin: 24px 0;
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
    }
  }
}

%Transition {
  transition: 0.2s cubic-bezier(0.55, 0.085, 0.68, 0.53);
}

%GradientTransition {
  background: linear-gradient(180deg, #bc9cff 0%, #8ba4f9 100%);
  @extend %Transition;
}

%DotPseudoClassInitial {
  content: "";
  position: absolute;
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;
  width: inherit;
  height: inherit;
  border-radius: inherit;
}

%BorderPseudoClassInitial {
  $border: 1px;
  content: "";
  position: absolute;
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;
  z-index: -1;
  margin: -$border;
  border-radius: inherit;
}

%Transform {
  &::before {
    opacity: 0;
  }
  &::after {
    opacity: 0.25;
  }
}

%DotStyle {
  width: 12px;
  height: 12px;
  border-radius: 10px;
  position: relative;
  @extend %Transition;
  &::before {
    @extend %DotPseudoClassInitial;
    @extend %GradientTransition;
  }
  &::after {
    @extend %DotPseudoClassInitial;
    background-color: $darkShade;
    @extend %Transition;
    opacity: 0;
  }
}

%BorderStyle {
  padding: 3px;
  position: relative;
  $border: 1px;
  background: #fff;
  background-clip: padding-box;
  border: solid $border transparent {
    radius: 2em;
  }
  &::before {
    @extend %BorderPseudoClassInitial;
    @extend %GradientTransition;
  }
  &::after {
    @extend %BorderPseudoClassInitial;
    background-color: $darkShade;
    @extend %Transition;
    opacity: 0;
  }
}

.options {
  display: flex;
}

.option {
  display: flex;
  align-items: center;
  margin: 5px 0;
  &:not(:last-of-type) {
    margin-right: 20px;
  }
  label {
    &:last-of-type {
      opacity: 0.75;
    }
  }
}

.radio-button {
  $radio-button: &;
  display: flex;
  align-items: center;
  label {
    &:first-of-type {
      margin-right: 10px;
    }
  }
  &__border {
    width: 20px;
    height: 20px;
    @extend %BorderStyle;
  }
  &__dot {
    @extend %DotStyle;
  }
  input[type="radio"] {
    display: none;
    &:not(:checked) ~ label {
      &:last-of-type {
        opacity: 0.5;
      }
      #{$radio-button}__border,
      #{$radio-button}__dot {
        @extend %Transform;
      }
      #{$radio-button}__dot {
        transform: scale(0);
      }
    }
  }
}

.toggle {
  margin-right: 10px;
  $toggle: &;
  #toggle {
    display: none;
    &:not(:checked) ~ label {
      #{$toggle}__button {
        transform: translateX(0px) scale(1);
      }
      #{$toggle}__button,
      #{$toggle}__border {
        @extend %Transform;
      }
    }
  }
  label {
    #{$toggle}__button {
      transform: translateX(20px) scale(1.2);
      @extend %DotStyle;
    }
    #{$toggle}__border {
      width: 40px;
      height: 20px;
      @extend %BorderStyle;
    }
  }
}

input[type="text"],
input[type="email"],
input[type="password"] {
  width: 100%;
  height: 44px;
  padding: 13px 15px;
  border: 1px solid $darkShade {
    radius: 4px;
  }
  opacity: 0.25;
  margin: 5px 0;
}

.form {
  position: absolute;
  background: #ffffff;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  padding: 40px 30px 30px;
  max-width: 380px;
  border: 1px solid rgba(0, 0, 0, 0.12);
  box-shadow: 0px 0px 25px rgba(0, 0, 0, 0.2);
  border-radius: 4px;
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
      color: $darkShade;
      opacity: 0.75;
    }
  }
  &__button-pay {
    margin: 15px 0;
    img {
      display: block;
    }
  }
  &__sign-in {
    display: flex;
    align-items: center;
    justify-content: space-between;
  }
}
</style>
