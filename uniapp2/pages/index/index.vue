<template>
	<view class="content">
		<image class="logo" src="/static/logo.png"></image>
		<view class="text-area">
			<text class="title">{{title}}</text>
			<!-- <navigator url="../zerjijeimian/zerjijeimian">跳转二级页面</navigator> -->
		</view>
	</view>
</template>

<script>
	var bitmap = null;
	export default {
		data() {
			return {
				title: '首页'
			}
		},
		onShow() {

		},
		onLoad() { 
		
		},
		methods: {

		}
		
	}
</script>
<style>
	.content {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
	}

	.logo {
		height: 200rpx;
		width: 200rpx;
		margin-top: 200rpx;
		margin-left: auto;
		margin-right: auto;
		margin-bottom: 50rpx;
	}

	.text-area {
		display: flex;
		justify-content: center;
	}

	.title {
		font-size: 36rpx;
		color: #8f8f94;
	}
</style>
