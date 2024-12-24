<template>
	<view class="out">
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
	
</script>

<style lang="scss">
.out{
	.box{
		width: 200px;
		height: 200px;
		background: pink;
	}
	.block{
		width: 200rpx;
		height: 200rpx;
		background: green;
	}
}

.scroll{
	border: 1px solid red;
	box-sizing: border-box;
	height: 100rpx;
	.group{
		white-space: nowrap;
		.item{
			width: 220rpx;
			height: 220rpx;
			background: royalblue;
			display: inline-block;
			margin-right: 10rpx;
		}
	}
}

.swiper{
	height: 350rpx;
	.item{
		padding: 20rpx;
		box-sizing: border-box;
		image{
			width: 100%;
			height: 330rpx;
			border-radius: 30rpx;
		}
	}
}
</style>
