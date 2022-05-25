<template>
	<view class="my-search-container" :style="{'background-color': bgcolor}" @click="searchBoxHandler">
		<view class="my-search-box" :style="{'border-radius': raduis + 'px'}">
			<uni-icons type="search" size="17"></uni-icons>
			<text class="placeholder">搜索</text>
		</view>

	</view>
</template>

<script>
	export default {
		name: "my-search",
		props: {
			bgcolor: {
				type: String,
				default: '#c00000'
			},
			raduis: {
				type: Number,
				default: 18
			}
		},
		data() {
			return {

			};
		},
		methods: {
			searchBoxHandler() {
				this.$emit('click')
			}
		}
	}
</script>

<style lang="scss">
	.my-search-container {
		display: flex;
		align-items: center;
		padding: 0 10px;
		height: 50px;
		// background-color: #c00000;

		.my-search-box {
			display: flex;
			justify-content: center;
			align-items: center;
			height: 36px;
			background-color: #fff;
			// border-radius: 18px;
			width: 100%;

			.placeholder {
				font-size: 15px;
				margin-left: 5px;
			}
		}
	}
</style>
