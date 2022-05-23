<template>
	<view>
		<view class="scroll-view-container">

			<!-- 左侧滑动区域 -->
			<scroll-view class="left-scroll-view" scroll-y="true" style="height: 300px;">

				<view></view>
			</scroll-view>
			<!-- 右侧滑动区域 -->
			<scroll-view scroll-y="true" style="height: 300px;">

				<view></view>
			</scroll-view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {

			};
		}
	}
</script>

<style lang="scss">
	.scroll-view-container {
		display: flex;
		.left-scroll-view{
			width: 120px;
		}
	}
</style>
