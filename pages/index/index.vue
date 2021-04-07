<template>
	<view>
		<view @click="onJump('/list/age-calculator/age-calculator')">年龄计算器</view>
	</view>
</template>

<script>
	export default {
		mounted(){
			
		},
		data() {
			return {
				
			}
		},
		methods: {
			onJump(url){
				uni.navigateTo({
					url
				})
			}
		}
	}
</script>

<style>

</style>
