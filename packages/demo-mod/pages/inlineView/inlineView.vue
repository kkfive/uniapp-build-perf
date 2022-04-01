<template>
		<view class="content">
			<view>你好，这是一个子页面</view>
			<view>
				<button @click="btnHandle">按钮</button>
			</view>
		</view>
</template>

<script>
	 const utilsVersion = 'v1.1.0-页面里测试版本'
	
	 function getMyName (){
		const name = '页面里的我的名字'
		console.log(`my name is ${name}`)
	}
	export default {
		data() {
			return {}
		},
		methods: {
			async	btnHandle(){
				console.log('当前版本：',utilsVersion)
				getMyName()
			}
		},
		onReady() {}
	}
</script>

<style lang="scss">
.content{
	margin-top: 100rpx;
	display: flex;
	justify-content: center;
	align-items: center;
	flex-direction: column;
}
</style>
