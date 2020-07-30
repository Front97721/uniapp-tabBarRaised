<script>
	export default {
		onLaunch: function() {  
		            console.log('App Launch');  
					 uni.onTabBarMidButtonTap(function() {
					 	uni.navigateTo({
					 		url: '/pages/circle/circle'
					 	})
					 })
		        },
		onShow: function() {
			console.log('App Show')
		},
		onHide: function() {
			console.log('App Hide')
		}
	}
</script>

<style>
	/*每个页面公共css */
</style>
