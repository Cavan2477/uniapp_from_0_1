<template>
	<view>
		<view class="out">
			<view class="row">
				<input class="border" type="text" placeholder="请输入您的名字" v-model="message.username"/>
			</view>
			<view class="row">
				<input class="border" type="text" placeholder="请输入您的电话号码" v-model="message.tel"/>
			</view>
			<view class="row">
				<textarea class="border" type="text" placeholder="请输入您的个人说明" v-model="message.content"/>
			</view>
			<view class="row">
				<button class="border" type="primary" @click="onsubmit">提交留言</button>
			</view>
			
			{{message}}
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				title: "测试uniapp",
				message: {
					username: "",
					tel: "",
					content: ""
				}
			};
		},
		methods: {
			onsubmit() {
				console.log(this.message);
			}
		}
	}
</script>

<style lang="scss">
.out {
	padding: 30rpx;
	.row {
		margin-bottom: 10rpx;
	}
	.border {
		border: 1px solid #eee;
		width: 100%;
		padding: 0 20rpx;
		min-height: 80rpx;
		box-sizing: border-box;
	}
}
</style>
