<template>
  <section class="main__contents">
    <h1 class="categoryHeading">
			{{ route.name }}
		</h1>
		<section class="grid product__container">
			<section class="grid__content">
				<section
					class="product"
					v-for="speaker in speakers"
					:key="speaker.name"
				>
					<picture>
						<source
							:srcset="`${getImageUrl(speaker.image.desktop)}`"
							media="(min-width: 992px)"
						/>
						<source
							:srcset="`${getImageUrl(speaker.image.tablet)}`"
							media="(min-width: 600px)"
						/>
						<img
							:src="`${getImageUrl(speaker.image.mobile)}`"
							:alt="speaker.name"
						/> 
					</picture>

					<section class="product__content">
						<small class="product__new" v-if="speaker.new"> new product</small>
						<h1 class="product__title">{{ speaker.name }}</h1>
						<p class="product__description">
							{{ speaker.description }}
						</p>

					<NuxtLink :to="`${route.name}/${speaker.slug}`" class="cta cta--prim">see product</NuxtLink>
					</section>
				</section>
        <BaseCategoryLinks class="categoryLinks shared"/>
			</section>
		</section>
    <AppAbout class="index"/>
  </section>
</template>

<script setup>
import jsonData from '~/static/data.json';
const route = useRoute();


const speakers = jsonData.filter(el => el.category === "speakers").reverse()

// console.log(speakers)

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
	/* width: 100%; */
	/* object-fit: cover; */

}
.categoryLinks {
  margin: 8em 0 1em;
}

@media (min-width: 900px){
  img {
    border-radius: 8px;
    height: 100%;
    flex: 1;
    object-fit: cover;
  }
}
</style>