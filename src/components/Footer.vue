<template>
  <div class="footer__wrapper">
    <div class="footer-outer">
      <div class="footer">
        <div class="footer__description">
          <div class="logo">
            <img class="icon" src="../assets/svg/logo.svg" alt="logo" />
            <img
              class="text"
              src="../assets/svg/logo_text.svg"
              alt="logo_text"
            />
          </div>
          <p class="footer__inc">
            Бронирование номеров в лучшем отеле 2019 года по версии ассоциации
            «Отельные взгляды»
          </p>
        </div>
        <div class="footer__navigation">
          <title class="footer__title">навигация</title>
          <div class="link"><p>О нас</p></div>
          <div class="link"><p>Новости</p></div>
          <div class="link"><p>Служба поддержки</p></div>
          <div class="link"><p>Услуги</p></div>
        </div>
        <div class="footer__about-us">
          <title class="footer__title">о нас</title>
          <div class="link"><p>О сервисе</p></div>
          <div class="link"><p>Наша команда</p></div>
          <div class="link"><p>Вакансии</p></div>
          <div class="link"><p>Инвесторы</p></div>
        </div>
        <div class="footer__support">
          <title class="footer__title">Служба поддержки</title>
          <div class="link"><p>Соглашения</p></div>
          <div class="link"><p>Сообщества</p></div>
          <div class="link"><p>Связь с нами</p></div>
        </div>
        <div class="footer__subscription">
          <title class="footer__title">Подписка</title>
          <div class="link">
            <p>Получайте специальные предложения и новости сервиса</p>
          </div>
          <div class="field">
            <input type="email" name="email" id="email" placeholder="Email" />
          </div>
        </div>
      </div>
    </div>
    <div class="footer__copyright-outer">
      <div class="footer__copyright">
        <p>Copyright © 2018 Toxin отель. Все права зачищены.</p>
        <div class="footer__socials">
          <img src="../assets/svg/twitter.svg" alt="Twitter Icon" />
          <img src="../assets/svg/facebook.svg" alt="Facebook Icon" />
          <img src="../assets/svg/instagram.svg" alt="Instagram Icon" />
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

.field {
  margin: 5px 0;
  margin-top: 20px;
  position: relative;
  &::before {
    content: "";
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

.footer {
  display: flex;
  justify-content: space-between;
  text-align: left;
  padding: {
    top: 100px;
    bottom: 100px;
  }
  &-outer {
    box-shadow: 0px 1px 0px rgba(31, 32, 65, 0.1);
    margin-bottom: 1px;
  }
  .link {
    margin: 0;
    margin-top: 15px;
  }
  &__title {
    @extend %H3;
    text-transform: uppercase;
  }
  > div:first-of-type,
  > div:last-of-type {
    max-width: 260px;
  }
  &__inc {
    opacity: 0.75;
    color: $darkShade;
    margin-top: 20px;
  }
  &,
  &__copyright {
    width: 100%;
    margin: auto;
    padding: {
      left: 15px;
      right: 15px;
    }
    max-width: 1200px;
  }
  &__copyright {
    height: 70px;
    display: flex;
    align-items: center;
    justify-content: space-between;
    &-outer {
      box-shadow: 0px 10px 20px rgba(31, 32, 65, 0.05);
      margin-top: 1px;
    }
  }
  &__socials {
    display: flex;
    img {
      display: block;
      &:not(:last-of-type) {
        margin-right: 20px;
      }
    }
  }
  &__wrapper {
    height: 443px;
    box-shadow: 0px 1px 0px rgba(31, 32, 65, 0.1);
  }
}
</style>
