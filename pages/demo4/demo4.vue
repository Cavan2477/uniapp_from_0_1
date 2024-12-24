<template>
	<view class="out">
		<form @submit="onSubmit">
			<view class="row">
				<input type="text" name="username" placeholder="请输入您的名字" />
			</view>
			<view class="row">
				<input type="text" name="tel" placeholder="请输入您的电话" />
			</view>
			<view class="row">
				<textarea name="content" id="" cols="30" rows="10" placeholder="请输入您的个人说明"></textarea>
			</view>

			<view class="row">
				<radio-group name="gender">
					<radio value="男">男</radio>
					<radio value="女">女</radio>
					<radio value="保密" checked="">保密</radio>
				</radio-group>
			</view>
			
			<view class="row">
				<picker :range="options" name="education" :value="selectOption" @change="pickerChange">
					<view class="">
						点击选择学历：{{ options[selectOption] }}
					</view>
				</picker>
			</view>

			<view class="btn">
				<button form-type="submit" type="primary">提交表单</button>
				<button form-type="reset">重置表单</button>
			</view>

			{{ obj }}
		</form>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				obj: null,
				options: ["高中", "大专", "本科", "硕士", "博士"],
				selectOption:  2
			};
		},
		methods: {
			onSubmit(e) {
				this.obj = e.detail.value;
				this.obj.education = this.options[this.selectOption];
			},
			pickerChange(e) {
				console.log(e)
				this.selectOption = e.detail.value;
			}
		}
	}
</script>

<style lang="scss">
	.out {
		padding: 20rpx;
		box-sizing: border-box;

		.row {
			border: 1px solid #eee;
			margin-bottom: 10rpx;
			min-height: 80rpx;
			align-content: center;
		}
	}
</style>