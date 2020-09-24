<template>
	<div class="main">
		<div class="main__background-image">
			<img src="../assets/images/background.png" alt="background" />
		</div>
		<Form />
	</div>
</template>

<script>
import Form from './Form';

export default {
	components: { Form },
};
</script>

<style lang="scss">
.main {
	&__background-image {
		max-height: 684px;
		overflow: hidden;
		display: flex;
		align-items: center;
		justify-content: center;
		& img {
			width: 100%;
		}
	}
}
</style>
