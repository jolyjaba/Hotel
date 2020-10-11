<template>
  <div class="form">
    <p class="form__title">Регистрация аккаунта</p>
    <TextField type="text" placeholder="Имя" />
    <TextField type="text" placeholder="Фамилия" />
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
    <p class="form__sub-title">дата рождения</p>
    <TextField type="text" placeHolder="ДД.ММ.ГГГГ" />
    <p class="form__sub-title">данные для входа в сервис</p>
    <TextField type="email" placeHolder="Email" />
    <TextField type="password" placeHolder="Пароль" />
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
    <Button text="перейти к оплате" type="filled directed" />
    <div class="form__footer">
      <p>Уже есть аккаунт на Toxin</p>
      <Button
        @click="$router.push('/login')"
        text="войти"
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

<style lang="scss">
@import "@/components/Fonts_Colors";

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
    @extend %Transition;
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
    cursor: pointer;
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
        transform: translateX(0px);
      }
      #{$toggle}__button,
      #{$toggle}__border {
        @extend %Transform;
      }
    }
  }
  label {
    cursor: pointer;
    #{$toggle}__button {
      transform: translateX(20px);
      @extend %DotStyle;
    }
    #{$toggle}__border {
      width: 40px;
      height: 20px;
      @extend %BorderStyle;
    }
  }
}
</style>
