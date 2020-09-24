<template>
	<div class="form">
		<p class="form__title">Регистрация аккаунта</p>
		<input type="text" class="form__name" placeholder="Имя" />
		<input type="text" class="form__surname" placeholder="Фамилия" />
	</div>
</template>

<script>
export default {};
</script>

<style lang="scss">
@import './Fonts_Colors';

.form {
	position: absolute;
    padding: 40px 30px 30px;
    max-width: 380px;
	&__title {
        @include H1();
        text-align: left;
    }
    &__name,
    &__surname {
        width: 100%;
    }
}
</style>
