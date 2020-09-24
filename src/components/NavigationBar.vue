<template>
	<div class="navigation-bar">
		<div class="navigation-bar__left-side">
			<div class="navigation-bar__logo">
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
			<div class="navigation-bar__button navigation-bar__button--sign-in">
				<p>войти</p>
			</div>
			<div class="navigation-bar__button navigation-bar__button--sign-up">
				<p>зарегистрироваться</p>
			</div>
		</div>
	</div>
</template>

<script>
export default {};
</script>

<style lang="scss">
@import './Fonts_Colors.scss';

.navigation-bar {
	max-width: 1200px;
	min-height: 70px;
	margin: auto;
	padding: 0 20px;
	display: flex;
	align-items: center;
	justify-content: space-between;
	&__left-side,
	&__right-side {
		display: flex;
		align-items: center;
	}
	&__logo {
		display: flex;
		.icon {
			margin-right: 12.5px;
		}
	}
	&__group {
		display: flex;
		& .link {
			& p {
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
	}
	&__button {
		padding: 7px 18px;
		margin-left: 20px;
		p {
			@include H3();
			text-transform: uppercase;
		}
		&--sign-in {
			width: 87px;
			background: #fff;
			color: $purple;
		}
		&--sign-up {
			width: 196px;
			color: #fff;
		}
		&--sign-in,
		&--sign-up {
			height: 34px;
			position: relative;
			box-sizing: border-box;
			$border: 2px;
			background-clip: padding-box;
			border: solid $border transparent;
			border-radius: 2em;
			&::before {
				content: '';
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
}
</style>
