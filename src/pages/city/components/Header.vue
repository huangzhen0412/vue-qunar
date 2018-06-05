<template>
	<div class="header">
		城市选择
		<router-link tag="div" to="/" class="iconfont back-icon">&#xe624;</router-link>
	</div>
</template>

<script>
export default {
	name: 'CityHeader'
}
</script>

<style lang="stylus" scoped>
	@import '~styles/varibles.styl'
	.header
		height $headerHeight
		line-height $headerHeight
		text-align center
		color #fff
		background $bgColor
		font-size .32rem
		position relative
		.back-icon
			width .64rem
			text-align center
			font-size .33rem
			color #fff
			position absolute
			top 0
			left .1rem
</style>