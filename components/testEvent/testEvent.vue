<template>
	<view>
		<input placeholder="请输入..." @input="onInput"/>
	</view>
</template>

<script>
	export default {
		name:"testEvent",
		data() {
			return {
				text: "默认值"
			};
		},
		methods: {
			onInput(e) {
				console.log(e.detail.value);
				this.$emit("inputChange", e.detail.value);
			}
		}
	}
</script>

<style lang="scss">

</style>