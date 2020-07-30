<template>
	<view>
		二级界面
	</view>
</template>

<script>
	export default {
		data() {
			return {
				
			};
		},
		onShow() {
			/* 隐藏凸起图标 */
			var icon = plus.nativeObj.View.getViewById("icon");
			setTimeout(function() {
				icon.hide();
			}, 100);
		}
	}
</script>

<style>

</style>
