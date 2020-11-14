<template>
	<view class="call">
		<image src="../../static/call/call_logo.jpg"></image>
		<view class="phone">
		<view @click="phone">联系电话：13671487174（点击拨打）</view>
		<view>校区地址：广东省东莞市南城区广东科技学院</view>
		</view>
		<map class="map" :scale="scale" :markers="markers" :longitude="longitude" :latitude="latitude"></map>
	</view>
</template>

<script>
	export default{
		data(){
			return{
				longitude:113.762141,
				latitude:22.978418,
				scale:13,
				markers:[
					{
						longitude:113.762141,
						latitude:22.978418,
						iconPath:'../../static/call/map.png',
						width:60,
						height:30
					}
				]
			}
		},
		methods:{
			phone(){
				uni.makePhoneCall({
					phoneNumber:'1367187174'
				})
			}
		}
	}
</script>

<style lang="scss">
	.call{
		image{
			width: 758rpx;
			height: 400rpx;
		}
		.phone{
			font-size: 30rpx;
			padding: 15rpx 20rpx;
			line-height: 80rpx;
			border-bottom: 1px solid #eee;
		}
		.map{
			width: 758rpx;
			height: 800rpx;
		}
	}
</style>
