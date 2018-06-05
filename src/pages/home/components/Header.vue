<template>
	<div class="header">
		<div class="header-left">
			<div class="iconfont back-icon">&#xe624;</div>
		</div>
		<div class="header-input">
			<span class="iconfont">&#xe632;</span>
			输入城市/景点/游玩主题
		</div>
		<router-link tag="div" to="/city" class="header-right">
			{{this.city}}
			<span class="iconfont arrow-icon">&#xe600;</span>
		</router-link>
	</div>
</template>

<script>
import { mapState } from 'vuex'
export default {
	name: 'HomeHeader',
	computed: {
		...mapState(['city'])
	}
}
</script>

<style lang="stylus" scoped>
	@import '~styles/varibles.styl'
	.header
		line-height $headerHeight
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
			padding 0 .1rem
			min-width 1.04rem
			text-align center
			.arrow-icon
				font-size .28rem
				margin-left -.05rem
</style>