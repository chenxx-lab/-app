<template>
	<view class="user">
		<view class="user_item1">
			<image src="../../static/user/user.jpg" class="icon0"></image>
			<text class="font1">管理者昵称<p @click="user">个人中心></p></text>
			<button><image src="../../static/user/money.png" class="icon1">拼单返现</image></button>
		</view>
		
		<view class="user_item2">
			<text class="font2">省钱月卡  已省43元</text>
			<text class="font3">></text>
		</view>
		
		<view class="user_item3">
			<text class="font4">我的订单</text>
			<text class="seeALL">查看全部></text>
		</view>
		
		<view class="user_item4">
			<view class="pay" v-for="(item,index) in orders" :key="index">
				<view><image :src="item.icon" class="icon2"></image></view>
			    <view class="font5">{{item.title}}</view>
			</view>
		</view>
		
		<view class="user_item4">
			<view class="pay" v-for="(item,index) in collect" :key="index">
				<view><image :src="item.icon" class="icon2"></image></view>
			    <view style="font-size: 30rpx;padding-left: 30rpx;color: #808080;">{{item.title}}</view>
			</view>
		</view>
		
		<view class="user_item4">
			<view class="pay" v-for="(item,index) in activities1" :key="index">
				<view><image :src="item.icon" class="icon2"></image></view>
			    <view style="font-size: 30rpx;padding-left: 20rpx;color: #808080;">{{item.title}}</view>
			</view>
		</view>
		
		<view class="user_item4">
			<view class="pay" v-for="(item,index) in activities2" :key="index">
				<view><image :src="item.icon" class="icon2"></image></view>
			    <view style="font-size: 30rpx;padding-left: 20rpx;color: #808080;">{{item.title}}</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default{
		data(){
			return{
				orders:[
					{icon:'../../static/user/prePay.png',title:'待付款',id:1},
					{icon:'../../static/user/preShall.png',title:'待分享',id:2},
					{icon:'../../static/user/pending_shipment.png',title:'待发货',id:3},
					{icon:'../../static/user/take_gooods.png',title:'待收货',id:4},
					{icon:'../../static/user/assess.png',title:'待评价',id:5},
				],
				collect:[
					{icon:'../../static/user/01.png',title:'优惠券',id:1},
					{icon:'../../static/user/02.png',title:'商品收藏',id:2},
					{icon:'../../static/user/03.png',title:'店铺收藏',id:3},
					{icon:'../../static/user/04.png',title:'历史浏览',id:4},
					{icon:'../../static/user/05.png',title:'退款售后',id:5},
				],
				activities1:[
					{icon:'../../static/user/activities/06.png',title:'小学果园',id:1},
					{icon:'../../static/user/activities/07.png',title:'看家免费',id:2},
					{icon:'../../static/user/activities/08.png',title:'天天领钱',id:3},
					{icon:'../../static/user/activities/09.png',title:'我爱消除',id:4},
					{icon:'../../static/user/activities/10.png',title:'小学牧场',id:5}
				],
				activities2:[
					{icon:'../../static/user/activities/01.png',title:'抢火车票',id:1},
					{icon:'../../static/user/activities/02.png',title:'收货地址',id:2},
					{icon:'../../static/user/activities/03.png',title:'我的评价',id:3},
					{icon:'../../static/user/activities/04.png',title:'官方客服',id:4},
					{icon:'../../static/user/activities/05.png',title:'我的设置',id:5},
				]
			}
		},
		methods:{
			user(){
				uni.navigateTo({
					url:'uni-center'
				})
			}
		}
	}
</script>

<style scoped>
	.user_item1{
		display: flex;
		width: 758rpx;
		height: 150rpx;
		margin-top: 10rpx;	
	}
	.icon0{
		width: 150rpx;
		height: 150rpx;
		border-radius: 50%;
		overflow: hidden;
	}
	.font1{
		padding-top: 25rpx;		
	}
	p{
		padding-left: 20rpx;
		padding-top: 20rpx;
		color: #999999;
		font-size: 20rpx;
	}
	button{
		width: 300rpx;
		height: 80rpx;
		font-size: 30rpx;
		display: flex;
		margin-top: 30rpx;
		margin-right: 10rpx;
		border-radius: 10px;
		border: 1px solid #fff;
		background: #FFFFFF;
	}
	.icon1{
		width: 100rpx;
		height: 80rpx;
		text-align: center;
	}
	
		
	.user_item2{
		margin-top: 50rpx;
		background: #FFE4C4;
		width: 758rpx;
		height: 80rpx;
		display: flex;
		border-radius: 15px;	
	}	
	.font2{
		padding: 15rpx 20rpx;	
		color: #DD524D;
	}	
	.font3{
		color: #DD524D;
		padding-left: 350rpx;
	}	
	 		
		
	.user_item3{
		margin-top:20rpx;					
	}
	.font4{
		padding:5rpx 30rpx;
		font-size: 30rpx;
	}	
	.seeALL{
		padding-left: 400rpx;
		font-size: 30rpx;
	}	
	
	
	.user_item4{
		width: 758rpx;
		height: 200rpx;
		display: flex;
	}	
	.pay{
		padding-top: 50rpx;
		
	}
	.icon2{
		width: 50rpx;
		height: 50rpx;
		padding: 30rpx 50rpx;
	}	
	.font5{
		font-size: 30rpx;
		color: #808080;
		padding: 0rpx 35rpx;
	}	
		
	
</style>
