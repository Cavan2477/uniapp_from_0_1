<template>
	<view class="out">
		<testitem></testitem>
		--------------输入框子组件内容修改-------------
		<testEvent @inputChange="onInputChange" @click.native="onTestEventClick"></testEvent>
		------------父子组件传值-----------
		<view>
			<button @click="onClickBtnStatePop">开启{{ statePop }}</button>
			<testPop :state.sync="statePop"></testPop>
		</view>
		
		-------------------------------
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

		<input type="text" v-model="title" />
		<view>原标题：{{title}}</view>
		<view>新标题：{{ changedTitle }}</view>
		<view>{{ inputTitle }}</view>

		<view class="add">
			<!-- <view class="row"> -->
			<input type="number" v-model="a" />
			<label>+</label>
			<input type="number" v-model="b" />
			<label>=</label>
			<label>{{ add }}</label>
			<!-- </view> -->
		</view>

		<view>
			<view>请输入新的名字：<input type="text" v-model="fullName"/></view>
			<view>全名：{{ fullName }}</view>
			<view>firstName: {{ firstName }}</view>
			<view>lastName: {{ lastName }}</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				obj: null,
				options: ["高中", "大专", "本科", "硕士", "博士"],
				selectOption: 2,
				title: "",
				titleText: "测试文本",
				a: 0,
				b: 0,
				firstName: 'Foo',
				lastName: 'Bar',
				statePop: false
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
			},
			onInputChange(e) {
				console.log(e);
			},
			onTestEventClick() {
				console.log("onTestEventClick原生方法输出...")
			},
			onClickBtnStatePop() {
				this.statePop = true;
			}
		},
		computed: {
			inputTitle: {
				set(newValue) {
					return newValue + "uniapp学习";
				}
			},
			changedTitle: {
				get() {
					return this.title.toLocaleUpperCase();
				}
			},
			add() {
				return Number(this.a) + Number(this.b);
			},
			fullName: {
				// getter
				get() {
					return this.firstName + ' ' + this.lastName
				},
				// setter
				set(newValue) {
					var names = newValue.split(' ')
					this.firstName = names[0]
					this.lastName = names[names.length - 1]
				}
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

	.add {
		display: flex;
		padding: 20rpx;
		box-sizing: border-box;
		justify-content: space-between;

		input {
			border: 1px solid #eee;
			align-content: center;
		}

		label {}

		// .row {
		// 	border: 1px solid #eee;
		// 	margin-bottom: 10rpx;
		// 	min-height: 80rpx;
		// 	align-content: center;
		// }
	}
</style>