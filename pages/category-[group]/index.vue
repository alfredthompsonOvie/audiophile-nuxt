<template>
	<section class="main__contents">
		<h1 class="categoryHeading">
			{{ route.params.group }}
		</h1>
		<section class="grid product__container">
			<section class="grid__content">
				<section class="product" v-for="item in products" :key="item.name">
					<picture>
						<source
							:srcset="`${getImageUrl(item.image.desktop)}`"
							media="(min-width: 992px)"
						/>
						<source
							:srcset="`${getImageUrl(item.image.tablet)}`"
							media="(min-width: 600px)"
						/>
						<img :src="`${getImageUrl(item.image.mobile)}`" :alt="item.name" />
					</picture>

					<section class="product__content">
						<small class="product__new" v-if="item.new"> new product</small>
						<h1 class="product__title">{{ item.name }}</h1>
						<p class="product__description">
							{{ item.description }}
						</p>

						<NuxtLink
							:to="`category-${route.params.group}/${item.slug}`"
							class="cta cta--prim"
							>see product</NuxtLink
						>
					</section>
				</section>
				<BaseCategoryLinks class="categoryLinks shared" />
			</section>
		</section>
		<AppAbout class="index" />
	</section>
</template>

<script setup>
const route = useRoute();

import jsonData from "~/static/data.json";

const products = jsonData
	.filter((el) => el.category === route.params.group)
	.reverse();

function getImageUrl(name) {
	return new URL(`/assets/images/${name}`, import.meta.url).href;
}
</script>

<style lang="scss" scoped>
.categoryLinks {
	grid-column: 2;
}
.categoryHeading {
	grid-column: 1/-1;
}
img {
	display: inline-block;
	margin-bottom: 2em;
	max-height: 450px;
}
.categoryLinks {
	margin: 8em 0 1em;
}

@media (min-width: 900px) {
	img {
		border-radius: 8px;
		height: 100%;
		flex: 1;
		object-fit: cover;
	}
}
</style>
