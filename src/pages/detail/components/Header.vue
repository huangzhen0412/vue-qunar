<template>
	<div class="header">
		<div class="header-abs" v-show="showAbs">
			<router-link tag="div" to="/" class="iconfont">&#xe624;</router-link>
		</div>
		<div class="header-fixed" v-show="!showAbs" :style="opacityStyle">
			景点详情
			<router-link tag="div" to="/" class="iconfont back-icon">&#xe624;</router-link>
		</div>
	</div>
</template>

<script>
export default {
	name: 'DetailHeader',
	data () {
		return {
			showAbs: true,
			opacityStyle: {
				opacity: 0
			}
		}
	},
	methods: {
		handleScroll () {
			const top = document.documentElement.scrollTop
			if(top > 60){
				this.showAbs = false
				let opacity = top / 150
				opacity = opacity > 1 ? 1 : opacity
				this.opacityStyle = { opacity }
			} else {
				this.showAbs = true
			}
		}
	},
	activated () {
		window.addEventListener('scroll', this.handleScroll)
	},
	deactivated () {
		window.removeEventListener('scroll', this.handleScroll)
	}
}
</script>

<style lang="stylus" scoped>
	@import '~styles/varibles.styl'
	.header-abs
		position absolute
		left .2rem
		top .2rem
		width .8rem
		height .8rem
		line-height .8rem
		border-radius 50%
		background rgba(0,0,0,.8)
		.iconfont
			text-align center
			color #fff
			font-size .35rem
	.header-fixed
		height $headerHeight
		line-height $headerHeight
		text-align center
		color #fff
		background $bgColor
		font-size .32rem
		position fixed
		top 0
		left 0
		right 0
		z-index 9
		.back-icon
			width .64rem
			text-align center
			font-size .33rem
			color #fff
			position absolute
			top 0
			left .1rem
</style>