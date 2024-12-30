<template>
	<view class="out">
		<view class="row" v-for="item in listArr" :key="item.id" @click="getItemDetail(item.id)">
			<view class="title">
				{{ item.title }}
			</view>
			<view class="content">
				{{ item.body }}
			</view>
		</view>
		<!-- <view v-for="item in picurl" :key="item.id" @click="getPicUrl">
			<image :src="item.url" mode="aspectFill"></image>
		</view> -->
	</view>
</template>

<script>
	export default {
		data() {
			return {
				picurl: "",
				listArr: []
			};
		},
		onLoad() {
			// this.getPicUrl();
			this.getData();
		},
		methods: {
			getPicUrl() {
				// let url = "https://dog.ceo/api/breeds/image/random";
				// let url = "http://jsonplaceholder.typicode.com/comments"; // 测试接口
				let url = "https://api.thecatapi.com/v1/images/search";

				uni.showLoading({
					title: "数据加载中..."
				})

				uni.request({
					url: url,
					timeout: 3000,
					data: {
						limit: 3
					},
					success: (res) => {
						console.log(res);

						this.picurl = res.data;
						uni.hideLoading();
					},
					fail: (err) => {
						console.log(err);
					},
					complete() {

					}
				})
			},
			getComment() {
				let url = "https://jsonplaceholder.typicode.com/posts/1";

				uni.request({
					url: url,
					success: (res) => {
						console.log(res);
					},
					fail: (err) => {
						console.log(err);
					},
					complete() {

					}
				})
			},
			getData() {
				uni.showLoading({
					title: "数据加载中...",
					mask: true,
				})
				
				let url = "https://jsonplaceholder.typicode.com/posts";
				
				uni.request({
					url: url,
					success: (res) => {
						console.log(res);
						this.listArr = res.data;
					},
					fail: (err) => {
						console.log(err);
					},
					complete() {
						uni.hideLoading()
					}
				})
			},
			getItemDetail(id) {
				uni.navigateTo({
					url: "/pages/detail/detail?id="+id,
				})
			},
		}
	}
</script>

<style lang="scss">
.out {
	padding: 50rpx 30rpx;
	.row {
		padding: 20rpx 0;
		border-bottom: 1px dotted #e4e4e4;
		.title {
			font-size: 36rpx;
			padding-bottom: 15rpx;
			color: #333;
		}
		.content {
			font-size: 28rpx;
			color: #888;
		}
	}
}
</style>