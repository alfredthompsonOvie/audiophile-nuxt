<template >
  <div class="main__contents">
    <section class="hero">
			<section class="hero__contents">
				<picture>
					<source
						srcset="~/assets/images/home/desktop/image-header.svg"
						media="(min-width: 992px)"
					/>
					<!-- <source
						srcset="~/assets/images/home/desktop/image-hero.jpg"
						media="(min-width: 992px)"
					/> -->
					<source
						srcset="~/assets/images/home/tablet/image-header.jpg"
						media="(min-width: 450px)"
					/>
					<img src="~/assets/images/home/mobile/image-header.jpg" alt="mark II headphones" />
				</picture>
				<section class="hero__details">
					<h1 class="subHeading">new product</h1>
					<h2 class="heading">xx99 mark ii headphones</h2>
					<p class="text">
						Experience natural, lifelike audio and exceptional build quality
						made for the passionate music enthusiast.
					</p>
          <NuxtLink to="" class="cta cta--prim">
            <span>see product</span>
          </NuxtLink>
					<!-- <router-link :to="{ name: 'productDetail', params: { id: 'headphones/xx99-mark-II-headphones' }}" class="cta cta--prim"
						>see product</router-link
					> -->
				</section>
			</section>
		</section>
  </div>
</template>

<script setup>

</script>

<style lang="scss" scoped>
.dropdown {
	padding-inline: 0;
}
.hero {
  grid-column: 1/-1;
  grid-row: 1;
	box-shadow: 0px 4px 4px rgba(0, 0, 0, 0.25);
	background-color: #0e0e0e;
}

.hero__details .heading {
	margin: 0.5em 0;
}
.hero__details .text {
	margin-bottom: 1.5em;
}
.category {
	margin-top: 5em;
}
.products {
	margin-top: 4em;
}
.product__speaker--zx9 {
	background-color: #d87d4a;

	padding: 3em 1em;
	text-align: center;
	color: #fff;
	background-image: url(@/assets/images/oval.svg);
	background-repeat: no-repeat;
	background-position: top center;
}
.product__speaker--zx9 h1 {
	max-width: 200px;
	margin: 0.5em auto;
}
.product__speaker--zx9 p {
	font-weight: 500;
	font-size: 15px;
	line-height: 25px;
	color: #ffffff;
	opacity: 0.75;
	margin: 0 auto 1.5em;
	max-width: 300px;
}
/* products */
.product__contents {
	border-radius: 8px;
	overflow: hidden;
}
.product__contents + .product__contents {
	margin-top: 2em;
}
.product--zx7-speakers {
	display: grid;
	grid-template-columns: repeat(2, 1fr);
	grid-template-rows: 12.5em;
	grid-template-rows: 18.5em;
	grid-template-rows: 15.5em;
	grid-template-rows: 320px;
	grid-template-rows: auto;
}
.product--zx7-speakers picture {
	grid-row: 1/-1;
	grid-column: 1/-1;

	background-color: red;
}
.product--zx7-speakers img {
	display: block;
	width: 100%;
	/* height: 320px; */

	/* object-fit: cover; */
}
.product__content--zx7 {
	grid-row: 1;
	grid-column: 1/-1;
	align-self: center;
	padding: 1em;
}
.heading--alt {
	font-weight: 700;
	font-size: clamp(22px, 3vw, 28px);
	line-height: 38px;
	letter-spacing: 2px;
	text-transform: uppercase;
	color: #000;
	margin-bottom: 0.8em;
}
.product--earphones {
	display: grid;
	grid-template-columns: 1fr;
	grid-template-rows: repeat(2, auto);
	gap: 1em;
	overflow: hidden;
}
.product--earphones img {
	border-radius: 8px;
	display: block;
	width: 100%;
}
.product__content--yx1 {
	/* text-align: center; */
	/* margin-top: 1em; */
	background: #f1f1f1;
	border-radius: 8px;
	padding: 2em;
}
@media (min-width: 600px) {
	.category {
		margin-top: 0em;
	}
	.products {
	margin-top: 0em;
}
	.btn--cart {
		margin-left: auto;
	}
	.product__speaker--zx9 {
		background-image: url(@/assets/images/oval-tablet.svg);
		background-size: contain;
	}
	.product__speaker--zx9 p {
		max-width: 350px;
	}
	.product__content--zx7 {
		padding-left: 3em;
	}
	.product--earphones {
		/* flex-direction: row; */
		display: grid;
		grid-template-columns: 1fr 1fr;
		grid-template-rows: auto;
	}
	/* .product--earphones img {
	flex: 1;
} */
	.product__content--yx1 {
		display: flex;
		flex-direction: column;
		align-items: flex-start;
		justify-content: center;
	}
}
@media (min-width: 600px) and (max-width: 992px) {
	.hero__contents img {
		/* width: 100%;
	height: 100%; */
		object-fit: cover;
		object-position: center;
	}
}

@media (min-width: 992px) {
	.hero {
		background-color: #121212;
		/* background-color: #1A1A1A; */
    /* background-color: #191919; */
	}
	.hero__contents {
		display: grid;
		/* grid-template-columns: 1fr 4fr 6fr 1fr; */
		grid-template-columns: 1fr 3fr 7fr 1fr;
		grid-template-rows: calc(100vh - 5em);
	}

	.hero__contents picture {
		/* grid-column: 3; */
		grid-column: 3/-1;
		grid-row: 1;
		/* width: 100%; */
	}
	.hero__contents img {
    object-position: center;
	}
	.hero__details {
		grid-column: 2;
		grid-row: 1;
		text-align: left;
		max-width: auto;
		margin: 0;
    
	}

  /* ----------------------------------------------------------------------------- */
	.product__speaker--zx9 {
		background-image: url(~/assets/images/oval-desktop.svg);
		background-position: left;
		background-size: contain;
		text-align: left;

		display: flex;
		align-items: flex-end;
		justify-content: center;
		gap: 6em;

		padding-bottom: 0em;
		padding-left: 5em;
		padding-right: 7em;
		overflow: hidden;
	}
	.product__speaker--zx9 img {
		align-self: flex-end;
		display: block;
	}
	.product__content {
		align-self: flex-start;
		/* margin-top: 1em; */
		/* border-radius: 0; */
	}
	.product__speaker--zx9 h1 {
		max-width: auto;
		margin-inline: 0;
		font-weight: 700;
		font-size: 56px;
		line-height: 58px;

		font-size: 40px;
		line-height: 40px;

		font-size: clamp(40px, 4vw, 56px);
		letter-spacing: 2px;
	}
	.product__speaker--zx9 p {
		margin-bottom: 2em;
	}
	.product__content--zx7 {
		padding-left: 5em;
	}
		.product__content--yx1 {
		padding-left: 5em;
	}
}

@media (min-width: 1350px) {
  .hero__contents {
		display: grid;
		grid-template-columns: 1fr 4fr 6fr 1fr;
		grid-template-rows: calc(100vh - 5em);
	}

	.hero__contents picture {
		grid-column: 3;
		grid-column: 3/-1;
		grid-row: 1;
		width: 100%;
	}
}

</style>