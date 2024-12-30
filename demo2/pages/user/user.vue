<template>
	<view>
		<view class="user" @click="clickUser">用户信息</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				
			};
		},
		methods: {
			clickUser() {
				uni.removeTabBarBadge({
					index: 2,
					text: ""
				})
			}
		},
		onLoad() {
			uni.setTabBarBadge({
				index: 2,
				text: "3"
			})
		}
	}
</script>

<style lang="scss">
.user {
	padding: 20rpx;
	border: 1rpx solid red;
	border-radius: 25rpx;
}
</style>
