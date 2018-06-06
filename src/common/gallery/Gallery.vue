<template>
	<div class="container">
		<div class="wrapper" @click="handleGalleryClick">
			<swiper :options="swiperOption">
				<swiper-slide v-for="(img, index) of imgs" :key="img">
					<img class="gallery-img" :src="img">
				</swiper-slide>
				<div class="swiper-pagination" slot="pagination"></div>
			</swiper>
		</div>
	</div>
</template>

<script>
export default {
	name: 'CommonGallery',
	props: {
		imgs: Array
	},
	data () {
		return {
			swiperOption: {
				pagination: {
					el: '.swiper-pagination',
					type: 'fraction'
				},
				observeParents: true,
				observer: true
			}
		}
	},
	methods: {
		handleGalleryClick () {
			this.$emit('close')
		}
	}
}
</script>

<style lang="stylus" scoped>
	.container >>> .swiper-container
		overflow inherit
	.container
		position fixed
		left 0
		right 0
		top 0
		bottom 0
		z-index 99
		background #000
		display flex
		flex-direction column
		justify-content center
		.wrapper
			background #fff
			// overflow hidden
			height 0
			padding-bottom 100%
			width 100%
			.gallery-img
				width 100%
			.swiper-pagination
				color #fff
				bottom -1rem
</style>