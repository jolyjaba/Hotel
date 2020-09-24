<template>
	<div>
		<Registration />
	</div>
</template>

<script>
import Registration from './views/Registration';

export default {
	components: { Registration },
};
</script>

<style lang="scss">
// @import './components/Fonts_Colors';

* {
	margin: 0;
	padding: 0;
	box-sizing: border-box;
}

#app {
	-webkit-font-smoothing: antialiased;
	-moz-osx-font-smoothing: grayscale;
	text-align: center;
}
</style>
