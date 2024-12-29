<template>
	<view class="pubTitle">
		<view class="big">
			{{ title }}
		</view>
		<view class="small">
			{{ subTitle }}
		</view>
		<view class="time">
			{{ time }}
		</view>
		<view>
			{{ list }}
		</view>
		<view>
			{{ user }}
		</view>
		<view class="line">
		</view>
	</view>
</template>

<script>
	export default {
		name:"pubTitle",
		// props: ["title", "subTitle"],
		props: {
			title: {
				type: String,
				default: "默认标题"
			},
			subTitle: {
				type: String,
				default: "默认副标题"
			},
			time: {
				type: String,
				default: Date.now()
			},
			list: {
				type: Array,
				default() {
					return [1,2,3]
				}
			},
			user: {
				type: Object,
				default() {
					return {
						name: "测试用户",
						gender: "保密"
					}
				}
			}
		},
		data() {
			return {
				
			};
		}
	}
</script>

<style lang="scss">
.pubTitle {
	padding: 60rpx 30rpx;
	text-align: center;
	background: darkkhaki;
	.big {
		font-size: 50rpx;
		font-weight: 600;
		color: #333;
	}
	.small {
		font-size: 28rpx;
		color: #888;
	}
	.line {
		display: inline-block;
		width: 80rpx;
		height: 8rpx;
		background: green;
		border-radius: 5rpx;
	}
}
</style>