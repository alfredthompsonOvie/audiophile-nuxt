<template>
	<nav class="grid navbar">
		<section class="grid__content navbar__contents">
			<TheHamburger @click="toggleMenu"/>

			<NuxtLink to="/" class="brand"><img src="~/assets/images/shared/audiophile.svg" alt="audiophile logo"></NuxtLink>

			<!-- mobile menu -->
			<BaseCategoryLinks  class="mobileMenu" v-show="isMenuOpen"/>


			<!-- -->
			<!-- desktop nav -->
			<BaseNavMenu v-if="!isMobile" />
			<!-- ^^^^^^^^^^menu^^^^^^^^^^^ -->

			<BaseCart />
			<div class="overlay" v-if="isMenuOpen"></div>
		</section>
	</nav>
</template>

<script setup>

const isMenuOpen = ref(false);
const windowWidth = ref(null);
const isMobile = ref(null);


function toggleMenu() {
	isMenuOpen.value = !isMenuOpen.value
}


function checkScreen() {
  windowWidth.value = window.innerWidth;
	if (windowWidth.value <= 991) {
		isMobile.value = true;
		isMenuOpen.value = false;
		return;
	}
	isMobile.value = false;
	isMenuOpen.value = false;
	return;
}
onMounted(() => {
  checkScreen();
  window.addEventListener("resize", checkScreen);
})
</script>

<style lang="scss" scoped>
.navbar {
	grid-column: 1/-1;
	grid-row: 1;
	background-color: #0e0e0e;
	border-bottom: 1px solid rgba(255, 255, 255, 0.1);
	height: 6em;
	z-index: 99;
}
.navbar__contents {
	display: flex;
	justify-content: space-between;
	align-items: center;

}
.brand {
	/* font-weight: 700; */
	position: relative;
	z-index: 99;
}
.mobileMenu {
	position: fixed;
	top: 0;
	left: 0;
	bottom: 0;
	width: 100%;
	display: grid;
	grid-template-columns: 1fr 10fr 1fr;
	grid-template-rows: 10em auto;
	z-index: 20;
}

.overlay {
	background-color: rgba(0, 0, 0, 0.4);
	position: fixed;
	top: 0;
	left: 0;
	right: 0;
	bottom: 0;
	height: 100%;
	width: 100%;
	z-index: 10;
}
@media (min-width: 600px) {
	.mobileMenu {
		position: absolute;
		top: 0;
		left: 0;
		bottom: 0;
		width: 100%;
		background-color: rgba(0, 0, 0, 0.2);
		display: grid;
		grid-template-columns: 1fr;
		grid-template-rows: 5em auto;
		z-index: 20;
	}
}
</style>
