<template>
	<view class="content">
		<image class="logo" src="/static/logo.png"></image>
		<view class="text-area">
			<!-- <text class="title">{{title}}</text> -->
			<navigator url="../zerjijeimian/zerjijeimian">跳转二级页面</navigator>
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
		onShow() { //显示突起图标
			var icon = plus.nativeObj.View.getViewById("icon");  //根据图标id取到图片
			if (icon) {
				setTimeout(function(){
					icon.show();
				},50)
			}
		},
		onLoad() { //加载图片
			//兼容ios端
			bitmap = new plus.nativeObj.Bitmap('bmp1');  //新增原生图片
			//bitmap.load('static/tab_icon_5.png', function() {}, function(e) {});  普通写法
			bitmap.loadBase64Data('data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAGQAAABkCAYAAABw4pVUAAAAGXRFWHRTb2Z0d2FyZQBBZG9iZSBJbWFnZVJlYWR5ccllPAAAA+tpVFh0WE1MOmNvbS5hZG9iZS54bXAAAAAAADw/eHBhY2tldCBiZWdpbj0i77u/IiBpZD0iVzVNME1wQ2VoaUh6cmVTek5UY3prYzlkIj8+IDx4OnhtcG1ldGEgeG1sbnM6eD0iYWRvYmU6bnM6bWV0YS8iIHg6eG1wdGs9IkFkb2JlIFhNUCBDb3JlIDUuNi1jMTM4IDc5LjE1OTgyNCwgMjAxNi8wOS8xNC0wMTowOTowMSAgICAgICAgIj4gPHJkZjpSREYgeG1sbnM6cmRmPSJodHRwOi8vd3d3LnczLm9yZy8xOTk5LzAyLzIyLXJkZi1zeW50YXgtbnMjIj4gPHJkZjpEZXNjcmlwdGlvbiByZGY6YWJvdXQ9IiIgeG1sbnM6eG1wPSJodHRwOi8vbnMuYWRvYmUuY29tL3hhcC8xLjAvIiB4bWxuczpkYz0iaHR0cDovL3B1cmwub3JnL2RjL2VsZW1lbnRzLzEuMS8iIHhtbG5zOnhtcE1NPSJodHRwOi8vbnMuYWRvYmUuY29tL3hhcC8xLjAvbW0vIiB4bWxuczpzdFJlZj0iaHR0cDovL25zLmFkb2JlLmNvbS94YXAvMS4wL3NUeXBlL1Jlc291cmNlUmVmIyIgeG1wOkNyZWF0b3JUb29sPSJBZG9iZSBQaG90b3Nob3AgQ0MgMjAxNyAoV2luZG93cykiIHhtcDpDcmVhdGVEYXRlPSIyMDE4LTAzLTA1VDE3OjAwOjEzKzA4OjAwIiB4bXA6TW9kaWZ5RGF0ZT0iMjAxOC0wMy0wNVQxNzowNToxOSswODowMCIgeG1wOk1ldGFkYXRhRGF0ZT0iMjAxOC0wMy0wNVQxNzowNToxOSswODowMCIgZGM6Zm9ybWF0PSJpbWFnZS9wbmciIHhtcE1NOkluc3RhbmNlSUQ9InhtcC5paWQ6NTQyRDNFQkQyMDU0MTFFOEEzQTI5NDk4NjhDNjY4QjMiIHhtcE1NOkRvY3VtZW50SUQ9InhtcC5kaWQ6NTQyRDNFQkUyMDU0MTFFOEEzQTI5NDk4NjhDNjY4QjMiPiA8eG1wTU06RGVyaXZlZEZyb20gc3RS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', function() {}, function(e) {});
			this.createtab();
		},
		methods: {
			createtab: function(){
				// 设置水平居中位置
				var leftPos = Math.ceil((plus.screen.resolutionWidth - 50) / 2);
				var view = new plus.nativeObj.View('icon', {
					bottom: '19px',
					left: leftPos + 'px',
					width: '50px',
					height: '50px'
				});
				//使用canvas画布把图标画到tabbar对应位置上
				view.drawBitmap(bitmap, {
					tag: 'font',
					id: 'icon',
					src: '/static/circle.png',
					position: {
						top: '0px',
						left: '5px',
						width: '50px',
						height: '100%'
					}
				});
				//监听界面跳转
				view.addEventListener("click", function(e) {
					uni.switchTab({
						url: '/pages/circle/circle'
					})
				}, false);
				view.show();
			}
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
