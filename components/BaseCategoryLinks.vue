<template>
	<section v-bind="$attrs">
		<ul class="dropdown">
			<li class="dropdown__item menuItem">
				<NuxtLink :to="{ name: 'headphones' }" class="dropdown__link">
					<img
						src="~/assets/images/shared/desktop/image-category-thumbnail-headphones.png"
						alt=""
						class="category__thumbnail"
					/>
					<p>Headphones</p>
					<span class="span__contents">
						<span class="span__text"> shop </span>

						<img
							src="~/assets/images/shared/desktop/icon-arrow-right.svg"
							alt=""
							class="icon-arrow-right"
						/>
					</span>
				</NuxtLink>
			</li>
			<li class="dropdown__item menuItem">
				<NuxtLink :to="{ name: 'speakers' }" class="dropdown__link">
					<img
						src="~/assets/images/shared/desktop/image-category-thumbnail-speakers.png"
						alt=""
						class="category__thumbnail"
					/>
					<p>Speakers</p>
					<span class="span__contents">
						<span class="span__text"> shop </span>
						<img
							src="~/assets/images/shared/desktop/icon-arrow-right.svg"
							alt=""
							class="icon-arrow-right"
						/>
					</span>
				</NuxtLink>
			</li>
			<li class="dropdown__item menuItem">
				<NuxtLink :to="{ name: 'earphones' }" class="dropdown__link">
					<img
						src="~/assets/images/shared/desktop/image-category-thumbnail-earphones.png"
						alt=""
						class="category__thumbnail"
					/>
					<p>Earphones</p>
					<span class="span__contents">
						<span class="span__text"> shop </span>
						<img
							src="~/assets/images/shared/desktop/icon-arrow-right.svg"
							alt=""
							class="icon-arrow-right"
						/>
					</span>
				</NuxtLink>
			</li>
		</ul>
	</section>
</template>

<script setup></script>

<style scoped>
/* mobile menu */
.mobileMenu .dropdown {
	grid-column: 2;
	grid-row: 2;

}
.mobileMenu .dropdown__item {
}
.mobileMenu .dropdown__link {
	position: relative;
	display: block;
	text-align: center;
	padding: 3em 2em 1em;
	font-size: 15px;
	transition: all 1s linear;
}
.span__contents {
	position: relative;
	display: inline-flex;
	align-items: center;
	justify-content: center;
	gap: 0.7em;
}
.icon-arrow-right {
	width: 0.7rem;
	/* transition: all 0.3s linear;
	filter: drop-shadow(0px 20px 8px rgba(0, 0, 0, 0.15)); */
}
.dropdown__item + .dropdown__item {
	margin-top: 4em;
}
.dropdown__link {
	background: #f1f1f1;
	border-radius: 8px;
}
.category__thumbnail {
	position: absolute;
	top: -4em;
	left: 50%;
	transform: translateX(-50%);
	width: 10em;
}

.dropdown__item:last-of-type .category__thumbnail {
	top: -3em;
}
.dropdown__link p {
	color: #000;
	text-transform: uppercase;
	font-weight: 700;
	letter-spacing: 1.07143px;
	line-height: 20px;
	margin-bottom: 0.7em;
	transition: all 0.3s linear;
}
.span__text {
	letter-spacing: 1px;
	text-transform: uppercase;
	color: #000000;
	mix-blend-mode: normal;
	opacity: 0.5;
	font-weight: 700;
	font-size: 13px;
	transition: all 0.3s linear;
}
.dropdown__link:hover .span__text {
	letter-spacing: 2px;
	color: #d87d4a;
}
/* .dropdown__item {
	background: #f1f1f1;
	border-radius: 8px;
} */

@media (min-width: 600px) {
	.categoryHeading {
		padding: 2em 0;
	}
	.mobileMenu .dropdown {
		align-items: flex-start;
		background-color: var(--white);
		height: 20em;
		grid-column: 1/-1;
	}
	.mobileMenu .dropdown__link {
		position: relative;
		display: block;
		text-align: center;
		padding: 5em 2em 2em;
		font-size: 15px;
		transition: all 1s linear;
	}

	/* --------------------------------------- */
	.dropdown {
		display: flex;
		align-items: center;
		justify-content: center;
		gap: 1em;
		padding: 5em 2em 4em;
		border-bottom-left-radius: 20px;
		border-bottom-right-radius: 20px;
		width: 100%;
	}
	.dropdown__item + .dropdown__item {
		margin-top: 0;
	}
	.dropdown__item {
		flex: 1;
	}
}

/* 







@media (min-width: 600px) {


	.mobileMenu .dropdown__link img {
		position: absolute;
		top: -45px;
		left: 50%;
		transform: translateX(-50%);
		transition: all 0.3s linear;
		width: 80px;
		filter: drop-shadow(0px 20px 8px rgba(0, 0, 0, 0.15));
	}
	.mobileMenu .dropdown__item:nth-child(3)  img {
		top: -30px;
	}
	.mobileMenu .dropdown__link:hover img {
		width: 6em;
	}

}

*/
</style>
