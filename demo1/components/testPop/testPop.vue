<template>
	<view>
		<view>---弹出框样式---</view>
		<view class="box" :style="{height: state ? '300rpx' : '0'}"></view>
		<button size="mini" @click="onClose">关闭</button>
	</view>
</template>

<script>
	export default {
		name:"testPop",
		props: {
			state: {
				type: Boolean,
				default: false
			},
		},
		data() {
			return {
				
			};
		},
		methods: {
			onClose() {
				console.log("onClose");
				this.$emit("update:state", false)
			}
		}
	}
</script>

<style lang="scss">
.box {
	width: 300rpx;
	height: 300rpx;
	background: #f00;
}
</style>