<template>
  <div>

  </div>
</template>

<script setup>

</script>

<style lang="scss" scoped>






/* nav menu */



/* VUE TRANSITION =======================================================*/
.fade-enter-from,
.fade-leave-to {
	opacity: 0;
}
.fade-enter-active,
.fade-leave-active {
	transition: 0.5s all linear;
}
@media (min-width: 600px) {
	nav {
		border-bottom: 0;
	}
	.navBar__content {
		border-bottom: 1px solid rgba(255, 255, 255, 0.1);
	}
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
@media (min-width: 600px) and (max-width: 991px) {
	.navBar__content {
		display: flex;
		justify-content: flex-start;
		align-items: center;
		gap: 2em;
	}
	/* .dropdown__overlay {
		padding: 5em 2em 4em;
	} */

	.btn--cart {
		margin-left: auto;
	}
	/* .overlay {
		background-color: rgba(0, 0, 0, 0.2);
		position: absolute;
		top: 0;
		left: 0;
		right: 0;
		bottom: 0;
		height: 100%;
		width: 100%;
		z-index: 10;
	} */
}
@media (min-width: 992px) {
	nav {
		background-color: #121212;
	}
}
</style>