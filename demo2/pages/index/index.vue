<template>
	<view class="content">
		<image class="logo" src="/static/logo.png"></image>
		<view class="text-area">
			<text class="title">{{title}}</text>
		</view>
		
		<view @click="onShowActionModel">显示Action模态框</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				title: 'Hello',
				actionItems: ['西游记', '红楼梦', '三国演义', '水浒传']
			}
		},
		onLoad() {

		},
		methods: {
			onShowActionModel() {
				uni.showActionSheet({
					itemList: this.actionItems,
					success: (res) => {
						console.log(this.actionItems[res.tapIndex]);
					}
				})
			}
		}
	}
</script>

<style>
	.content {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
	}

	.logo {
		height: 200rpx;
		width: 200rpx;
		margin-top: 200rpx;
		margin-left: auto;
		margin-right: auto;
		margin-bottom: 50rpx;
	}

	.text-area {
		display: flex;
		justify-content: center;
	}

	.title {
		font-size: 36rpx;
		color: #8f8f94;
	}
</style>
