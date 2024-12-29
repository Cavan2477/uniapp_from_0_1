<template>
	<view class="out">
		<view>
			--------跳转页面测试--------
			<view>
				<button size="mini" @click="onClickGoList">go [列表]</button>
			</view>
			<view>
				<button size="mini" @click="onClickGoAbout">go [我们]</button>
			</view>
			<view>
				<button size="mini" @click="onClickGoDemo">go [demo]</button>
			</view>
			<view>
				<button size="mini" @click="onClickGoDemo2">go [demo2]</button>
			</view>
			<view>
				<button size="mini" @click="onClickGoDemo4">go [demo4]</button>
			</view>
		</view>
		
		<pubTitle :title="title" :subTitle="subTitle" :time="time" :list="list" :user="user"></pubTitle>

		<navigator url="/pages/list/list" open-type="redirect">新闻列表</navigator>
		<navigator url="/pages/about/about" open-type="reLaunch">关于</navigator>

		<button type="warn">确认提交</button>
		<button size="mini" type="primary">确认提交</button>

		<video src="/static/video/pretty_girl.mp4"></video>

		<!-- <view class="box">div</view>
		<view class="block">div</view> -->

		<icon type="success" size="26"></icon>
		<icon type="waiting" size="26"></icon>

		<view>uniapp</view>
		<view>web前端</view>

		<text user-select selectable>nodejs span</text>
		<text space="ensp" decode>vue &gt; js</text>

		<scroll-view class="scroll" scroll-x scroll-y>
			<view class="group">
				<view class="item">
					111
				</view>
				<view class="item">
					222
				</view>
				<view class="item">
					333
				</view>
				<view class="item">
					444
				</view>
				<view class="item">
					555
				</view>
			</view>
		</scroll-view>

		<swiper class="swiper" circular autoplay interval="2000" indicator-dots>
			<swiper-item class="item">
				<image src="/static/swiper1.jpeg" mode="aspectFill"></image>
			</swiper-item>
			<swiper-item class="item">
				<image src="/static/swiper2.jpeg" mode="aspectFill"></image>
			</swiper-item>
			<swiper-item class="item">
				<image src="/static/swiper3.jpeg" mode="aspectFill"></image>
			</swiper-item>
			<swiper-item class="item">
				<image src="/static/swiper4.jpeg" mode="aspectFill"></image>
			</swiper-item>
		</swiper>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				title: "首页",
				subTitle: "index page",
				time: Date.now(),
				list: [4,5,6],
				user: {
					name: "张三",
					gender: "男"
				}
			}
		},
		methods: {
			onClickGoList() {
				uni.reLaunch({
					url: "/pages/list/list",
					success: res => {
						console.log(res);
					}
				})
			},
			onClickGoAbout() {
				uni.reLaunch({
					url: "/pages/about/about",
					success: res => {
						console.log(res);
					}
				})
			},
			onClickGoDemo() {
				uni.navigateTo({
					url: "/pages/demo/demo",
					animationType:'slide-in-bottom',
					animationDuration: 1000,
					success: res => {
						console.log(res);
					}
				})
			},
			onClickGoDemo2() {
				uni.navigateTo({
					url: "/pages/demo2/demo2",
					animationType:'zoom-fade-out',
					animationDuration: 1000,
					success: res => {
						console.log(res);
					}
				})
			},
			onClickGoDemo4() {
				uni.switchTab({
					url: "/pages/demo4/demo4",
					success: res => {
						console.log(res);
					}
				})
			},
		}
	}
</script>

<style lang="scss">
	.out {
		.box {
			width: 200px;
			height: 200px;
			background: pink;
		}

		.block {
			width: 200rpx;
			height: 200rpx;
			background: green;
		}
	}

	.scroll {
		border: 1px solid red;
		box-sizing: border-box;
		height: 100rpx;

		.group {
			white-space: nowrap;

			.item {
				width: 220rpx;
				height: 220rpx;
				background: royalblue;
				display: inline-block;
				margin-right: 10rpx;
			}
		}
	}

	.swiper {
		height: 350rpx;

		.item {
			padding: 20rpx;
			box-sizing: border-box;

			image {
				width: 100%;
				height: 330rpx;
				border-radius: 30rpx;
			}
		}
	}
</style>