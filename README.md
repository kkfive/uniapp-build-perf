## 说明

这是一个问题的demo库。

如果您也遇到了同样问题并且已有解决方案，还请麻烦告知如何解决

如果您是uniapp维护者也请麻烦告知下如何解决

## 问题简单描述

在分包中引入的js文件（外部引入的）则**会**打包到主包的`vender.js`中

![image-20220401153441291](https://file.acs.pw/lsky/2/2022/04/01/6246ab1cb8e70.png)

而直接写在页面的代码，例如：

```vue
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
```

如果直接写在代码里则**不会**打包进`vender.js`中。

**因此，引入的外部js文件如何不被打包进主包。**按照[2019年的issue回答](https://github.com/dcloudio/uni-app/issues/649#issuecomment-528381717)，我不理解其中第二条，何为“当某个 js 仅被一个分包引用时，该 js 会被打包到该分包内”。



