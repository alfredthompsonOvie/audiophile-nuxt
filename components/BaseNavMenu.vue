<template>
	<ul class="nav__menu">
		<li><NuxtLink to="/">Home</NuxtLink></li>
		<li><NuxtLink to="/category-headphones">Headphones</NuxtLink></li>
		<li><NuxtLink to="/category-speakers">Speakers</NuxtLink></li>
		<li><NuxtLink to="/category-earphones">Earphones</NuxtLink></li>
	</ul>
</template>

<script setup></script>

<style lang="scss" scoped>
.nav__menu {
	display: flex;
	flex-direction: column;
	align-items: center;
	gap: 0.6em;
}
.nav__menu a {
	font-size: 13px;
	line-height: 25px;
	letter-spacing: 2px;
	position: relative;
}
.router-link-exact-active {
	color: var(--main-hover);
	font-weight: 700;
}
.nav__menu a::before {
	content: "";
	position: absolute;
	width: 0%;
	height: 150%;
	left: 50%;
	transition: all 0.3s linear;
	background-color: var(--main-hover);
	/* mix-blend-mode: multiply; */
	mix-blend-mode: darken;
}

.nav__menu a:hover::before {
	left: 0%;
	width: 100%;
}

@media (min-width: 600px) {
	.nav__menu {
		display: flex;
		flex-direction: row;
		align-items: center;
		gap: 2em;
	}
}
</style>
