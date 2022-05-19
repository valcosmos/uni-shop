<template>
	<view>
		<!-- swiper -->
		<swiper :indicator-dots="true" :autoplay="true" :interval="3000" :duration="1000" :circular="true">
			<swiper-item v-for="(item, i) in swiperList">
				<view class="swiper-item">
					<image :src="item.image_src" mode=""></image>
				</view>
			</swiper-item>
			<swiper-item>
				<view class="swiper-item"></view>
			</swiper-item>
		</swiper>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				// 这是轮播图数据列表
				swiperList: []
			};
		},
		onLoad() {
			// 调用方法 获取轮播图数据
			this.getSwiperList()
		},
		methods: {
			async getSwiperList() {
				const {
					data: res
				} = await uni.$http.get('/api/public/v1/home/swiperdata')
				if (res.meta.status !== 200) {
					return uni.showToast({
						title: '数据请求失败',
						// 1.5s
						duration: 1500,
						icon: 'none'
					})
				}
				this.swiperList = res.message
			}
		}
	}
</script>

<style lang="scss">
	swiper {
		height: 330rpx;

		.swiper-item,
		image {
			width: 100%;
			height: 100%;
		}
	}
</style>
