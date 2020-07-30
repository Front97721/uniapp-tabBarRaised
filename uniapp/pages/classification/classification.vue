<template>
	<view>
		分类
	</view>
</template>

<script>
	export default {
		data() {
			return {
				
			};
		},
		onShow() {
			var icon = plus.nativeObj.View.getViewById("icon");
			if (icon) {
				setTimeout(function(){
					icon.show();
				},100)
			}
		},
	}
</script>

<style>

</style>
