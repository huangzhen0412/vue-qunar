<template>
	<div class="header">
		<div class="header-left">
			<div class="iconfont back-icon">&#xe624;</div>
		</div>
		<div class="header-input">
			<span class="iconfont">&#xe632;</span>
			输入城市/景点/游玩主题
		</div>
		<div class="header-right">
			城市
			<span class="iconfont arrow-icon">&#xe600;</span>
		</div>
	</div>
</template>

<script>
export default {
	name: 'HomeHeader'
}
</script>

<style lang="stylus" scoped>
	@import '~styles/varibles.styl'
	.header
		line-height .86rem
		background $bgColor
		display flex
		color #fff
		.header-left
			width .64rem
			.back-icon
				text-align center
		.header-input
			flex 1
			background #fff
			margin-left .2rem
			margin-top .12rem
			padding-left .24rem
			height .64rem
			line-height .64rem
			border-radius .1rem
			color #bbb
		.header-right
			width 1.24rem
			text-align center
			.arrow-icon
				font-size .28rem
				margin-left -.05rem
</style>