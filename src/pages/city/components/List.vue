<template>
	<div class="list" ref="wrapper">
		<div>
			<div class="area">
				<div class="title border-topbottom">当前城市</div>
				<div class="button-list">
					<div class="button-wrapper" @click="goBack">
						<div class="button">{{this.currentCity}}</div>
					</div>
				</div>
			</div>
			<div class="area">
				<div class="title border-topbottom">热门城市</div>
				<div class="button-list">
					<div class="button-wrapper" v-for="city of hotCities" :key="city.id" @click="handleCityClick(city.name)">
						<div class="button">{{city.name}}</div>
					</div>
				</div>
			</div>
			<div class="area" v-for="(city, key) of cities" :key="key" :ref="key">
				<div class="title border-topbottom">{{key}}</div>
				<div class="item-list">
					<div class="item border-bottom" v-for="item of city" :key="item.id" @click="handleCityClick(item.name)">{{item.name}}</div>
				</div>
			</div>
		</div>
	</div>
</template>

<script>
import Bscroll from 'better-scroll'
import { mapState, mapMutations } from 'vuex'
export default {
	name: 'CityList',
	props: {
		hotCities: Array,
		cities: Object,
		letter: String
	},
	computed: {
		...mapState({
			currentCity: 'city'
		})
	},
	methods: {
		handleCityClick (city) {
			// this.$store.dispatch('changeCity', city)
			// this.$store.commit('changeCity', city)
			this.changeCity(city)
			this.$router.push('/')
		},
		...mapMutations(['changeCity']),
		goBack () {
			this.$router.push('/')
		}
	},
	mounted () {
		this.scroll = new Bscroll(this.$refs.wrapper)
	},
	watch: {
		letter () {
			if(this.letter){
				const element = this.$refs[this.letter][0]
				this.scroll.scrollToElement(element)
			}
		}
	}
}
</script>

<style lang="stylus" scoped>
	@import '~styles/varibles.styl'
	.border-topbottom
		&:before
			border-color #ccc
		&:after
			border-color #ccc
	.border-bottom
		&:before
			border-color #ccc
	.list
		position absolute
		top 1.58rem
		right 0
		left 0
		bottom 0
		overflow hidden
		.title
			line-height .54rem
			background #eee
			padding-left .2rem
			font-size .26rem
			color #666
		.button-list
			padding .1rem .5rem .1rem .1rem
			overflow hidden
			.button-wrapper
				float left
				width 33.33%
				.button
					margin .1rem
					padding .1rem 0
					text-align center
					border .02rem solid #ccc
					broder-radius .06rem
		.item-list
			.item
				line-height .76rem
				padding-left .2rem
</style>