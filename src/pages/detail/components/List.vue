<template>
	<div class="container">
		<div class="item" v-for="(item, index) of list" :key="index">
			<div class="item-title border-bottom">
				<span class="item-title-icon"></span>
				{{item.title}}
			</div>
			<div class="item-children" v-if="item.children">
				<detail-list :list="item.children"></detail-list>
			</div>
		</div>
	</div>
</template>

<script>
export default {
	name: 'DetailList',
	props: {
		list: Array
	}
}
</script>

<style lang="stylus" scoped>
	@import '~styles/varibles.styl'
	.item-title
		line-height .8rem
		font-size .32rem
		display flex
		padding-left .2rem
		.item-title-icon
			display block
			width .36rem
			height .36rem
			background url(http://s.qunarzz.com/piao/image/touch/sight/detail.png) 0 -.45rem no-repeat
			margin-right .1rem
			background-size .4rem 3rem
			position relative
			left .06rem
			top .2rem
	.item-children
		padding 0 .3rem
</style>