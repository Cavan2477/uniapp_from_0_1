<template>
	<view class="">
		<view class="detail">
			<view class="title">
				{{ objData.title }}
			</view>
			<view class="content">
				{{ objData.body }}
			</view>
		</view>
		<!-- 评论 -->
		<view class="comments">
			<view class="text">
				评论
			</view>
			<view class="row" v-for="item in comments" :key="item.id">
				<view class="top">
					<view class="name">{{ item.name }}</view>
					<view class="email">{{ item.email }}</view>
				</view>
				<view class="content">
					{{ item.body }} 111
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				objData: {},
				id: 1,
				comments: []
			};
		},
		onLoad(e) {
			console.log(e);

			this.getDetail(e.id);
			this.getComments(e.id);
		},
		methods: {
			getDetail(id) {
				let url = "https://jsonplaceholder.typicode.com/posts/" + id;

				uni.showLoading({
					title: "数据加载中...",
					mask: true,
				})

				uni.request({
					url: url,
					success: res => {
						console.log(res);
						this.objData = res.data;
					},
					complete() {
						uni.hideLoading();
					}
				})
			},
			getComments(id) {
				uni.showLoading({
					title: "评论获取中...",
					mask: true,
				})
				
				let url = `https://jsonplaceholder.typicode.com/posts/${id}/comments`;
				
				uni.request({
					url: url,
					success: (res) => {
						console.log(res);
						
						this.comments = res.data;
					}
				})
			}
		}
	}
</script>

<style lang="scss">
	.detail {
		padding: 30rpx;

		.title {
			font-size: 46rpx;
			color: #000;
			padding-bottom: 20rpx;
		}

		.content {
			font-size: 30rpx;
			color: #666;
		}
	}
	.comments {
		font-size: 46rpx;
		padding: 30rpx;
		background: #f8f8f8;
		.text {
			
		}
		.row {
			font-size: 28rpx;
			padding: 30rpx 20rpx;
			border-bottom: 1rpx solid #e8e8e8;
			padding: 20rpx 0;
			.top {
				font-size: 22rpx;
				display: flex;
				justify-content: space-between;
				padding-bottom: 15rpx;
				color: #666;
			}
			.content {
				font-size: 28rpx;
				color: #555;
			}
		}
	}
</style>