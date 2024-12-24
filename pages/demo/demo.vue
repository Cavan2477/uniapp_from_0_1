<template>
	<view>
		---v-html----
		<view v-html="code">
		</view>
		
		---v-bind----
		<!-- <image :src="'../../static/swiper'+ item +'.jpeg'" v-for="item in [1,2,3,4]"></image> -->
		
		<view class="box" :style="{background: bgcolor}" @click="clickBg">
			{{ randam }}
		</view>
		
		<view class="block" :class="{myactive:state}" @click="clickBlock">
		</view>
		
		<view class="block" :class="state ? 'myactive' : ''" @click="clickBlock">
		</view>
		
		<view class="nav">
			<view class="item" :class="navIndex == index ? 'itemActive' : ''" v-for="(item, index) in navArr" :key="item.id" 
			@click="clickNavItem(index)">
				{{item.title}}
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				code: "<h1>uniapp学习</h1>",
				img: "../../static/logo.png",
				bgcolor: "#22ee00",
				randam: 0,
				state: false,
				navArr: [
					{id:1,title:"首页"},
					{id:2,title:"介绍"},
					{id:3,title:"教程"},
					{id:4,title:"组件"}
				],
				navIndex: 0,
				itemState: false,
			};
		},
		methods: {
			clickBg() {
				let color = "#" + String(Math.random()).substring(3,6);
				console.log(color);
				
				this.bgcolor = color
				
				this.randam = String(Math.random()).substring(3,6);
			},
			clickBlock() {
				this.state = !this.state;
			},
			clickNavItem(index) {
				console.log(index);
				this.navIndex = index;
			}
		}
	}
</script>

<style lang="scss">
.box {
	width: 200rpx;
	height: 200rpx;
	background:pink;
}

.block {
	width: 300rpx;
	height: 300rpx;
	background: blue;
} 

.myactive {
	width: 400rpx;
	background: hotpink;
	border-radius: 20rpx;
} 
.nav {
	display: flex;
	justify-content: space-around;
	align-content: center;
	.item {
		flex: 1;
		line-height: 90rpx;
		text-align: center;
		background: #ccc;
		&.itemActive {
			background: #1AA034;
			transition: 0.4s;
			color: #fff;
		}
	}
}
</style>
