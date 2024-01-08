<template>
  <button
  @click="toggleCart"
  class="btn-cart"
  >
    <img src="~/assets/images/shared/desktop/icon-cart.svg" alt="cart icon">
    <span class="itemsInCart" v-show="count !== 0">{{ count }}</span>
  </button>
</template>

<script setup>

const count = ref(0)

function toggleCart() {
  
}
</script>

<style lang="scss" scoped>
.btn-cart {
  position: relative;
}
.itemsInCart {
	color: var(--grayishWhite);
	background-color: var(--main);
	position: absolute;
	top: -0.8em;
	left: 1.6em;
	padding: 0.25em;
	border-radius: 50%;
	font-size: 0.7rem;
}
</style>