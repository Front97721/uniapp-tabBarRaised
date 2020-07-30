<template>
	<view>
		我的jiemain 
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
				},50)
			}
		},
		onHide() {
			
		}
	}
</script>

<style>

</style>
