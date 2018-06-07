<template>
	<div>
		<div class="banner" @click="handleBannerClick">
			<img class="banner-img" :src="bannerImg">
			<div class="banner-info">
				<div class="banner-title">{{sightName}}</div>
				<div class="banner-number"><span class="iconfont">&#xe61b;</span><span>{{gallaryImgs.length}}</span></div>
			</div>
		</div>
		<fade-animation>
			<common-gallery :imgs="gallaryImgs" v-show="showGallery" @close="handleGalleryClose"></common-gallery>
		</fade-animation>
	</div>
</template>

<script>
import CommonGallery from 'common/gallery/Gallery'
import FadeAnimation from 'common/animation/FadeAnimation'
export default {
	name: 'DetailBanner',
	components: {
		CommonGallery,
		FadeAnimation
	},
	props: {
		sightName: String,
		bannerImg: String,
		gallaryImgs: Array
	},
	data () {
		return {
			showGallery: false
			/*imgs: ['http://img1.qunarzz.com/sight/p0/201404/23/04b92c99462687fa1ba45c1b5ba4ad77.jpg_800x800_70debc93.jpg','http://img1.qunarzz.com/sight/p0/1709/76/7691528bc7d7ad3ca3.img.png_800x800_9ef05ee7.png']*/
		}
	},
	methods: {
		handleBannerClick () {
			this.showGallery = true
		},
		handleGalleryClose () {
			this.showGallery = false
		}
	}
}
</script>

<style lang="stylus" scoped>
	.banner
		overflow hidden
		height 0
		padding-bottom 55%
		position relative
		.banner-img
			width 100%
		.banner-info
			position absolute
			left 0
			right 0
			bottom 0
			display flex
			line-height .6rem
			color #fff
			background-image linear-gradient(top, rgba(0,0,0,0), rgba(0,0,0,.7))
			.banner-title
				flex 1
				font-size .35rem
				padding-left .3rem
			.banner-number
				padding 0 .4rem
				line-height .4rem
				height .4rem
				border-radius .2rem
				background rgba(0,0,0,.6)
				margin-top .08rem
				.iconfont
					margin-right .1rem
</style>