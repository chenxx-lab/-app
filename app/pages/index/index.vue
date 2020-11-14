<template>
	<view class="home">
		 <!-- 轮播图 -->
		<view>
		  <swiper indicator-dots circular autoplay @click="goodsList">
				<swiper-item><image src="../../static/swiper_icon/01.jpg"></image></swiper-item>
				<swiper-item><image src="../../static/swiper_icon/02.jpg"></image></swiper-item>
				<swiper-item><image src="../../static/swiper_icon/03.jpg"></image></swiper-item>
				<swiper-item><image src="../../static/swiper_icon/04.jpg"></image></swiper-item>
			</swiper>
		</view>
         <!-- 导航栏 -->
		<view class="nav">
			<view class="nav-item" v-for="(item,index) in navs" :key="index" @click="NavItemClick(item.path)">
				<view class="iconfont"><image :src=item.icon></image></view>
				<text>{{item.title}}</text>
			</view>
	
		</view>
	
	    <!-- 推荐商品 -->
	    <view class="hot_goods">
		<view class="title">推荐商品</view>
	
	    <!-- 推荐商品列表 -->
	    <view class="goods_list">
		<view class="goods_item" v-for="(item,index) in goods_list" 
		@click="goodsList"
		:key="index">
			<view><image :src=item.image></image></view>
			<view class="price">
				<text>{{item.sellPrice}}</text>
				<text>{{item.prePrice}}</text>
			</view>
			<view>
				<text>{{item.title}}</text>
			</view>
		</view>
	    </view>
		
		<!-- 底部 -->
		<view style="font-size: 20rpx;color: #C0C0C0;text-align: center;margin-top: 50rpx;">
			人家也是有底线的
		</view>
	</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				navs:[
				{
					icon:'../../static/nav_icon/shoppermaket.png',
					title:'小学超市',
					path:'/pages/market/market'
				},
				{
					icon:'../../static/nav_icon/community.png',
					title:'社区图片',
					path:'/pages/community/community'
				},
				{
					icon:'../../static/nav_icon/video.png',
					title:'学习视频',
					path:'/pages/video/video'
				},
				{
					icon:'../../static/nav_icon/call.png',
					title:'联系客服',
					path:'/pages/call/call'
				}
				],
				goods_list:[
					{
						image:'../../static/goods_icon/04.jpg',
						sellPrice:'￥1522',
						prePrice:'￥5664',
						title:'联想笔记本耐用耐摔防水多场合使用笔记本'
					},
					{
						image:'../../static/goods_icon/01.jpg',
						sellPrice:'￥785',
						prePrice:'￥9668',
						title:'美的全智能自动化家庭版冰箱节能节电'
					},
					{
						image:'../../static/goods_icon/02.jpg',
						sellPrice:'￥754',
						prePrice:'￥2553',
						title:'联想笔记本电脑柯南壁纸显示屏'
					},
					{
						image:'../../static/goods_icon/03.jpg',
						sellPrice:'￥1420',
						prePrice:'￥5896',
						title:'多功能热水壶节能节电防漏电'
					}
				]
			}
			
		},
		onLoad: function (options) {
		        setTimeout(function () {
		            console.log('start pulldown');
		        }, 1000);
		        uni.startPullDownRefresh();
		    },
		onPullDownRefresh() {
			        console.log('refresh');
			        setTimeout(function () {
			            uni.stopPullDownRefresh();
			        }, 1000);
			    },
		methods: {
         goodsList(){
			 uni.navigateTo({
			 	url:'../detail/detail'
			 })
		 },
		 NavItemClick(url){
			 uni.navigateTo({
			 	url
			 })
		 }
		}
	}
</script>

<style lang="scss">
	.home{
		swiper{
			width: 758rpx;
			height: 380rpx;
			image{
				width: 100%;
				height: 100%;
			}			
		}
		.nav{
			display: flex;
			margin-top: 15rpx;
			.nav-item{
				text-align: center;
				width: 25%;
				view{
					margin-left: 35rpx;
					width: 120rpx;
					height: 120rpx;
					background-color: #DC143C;
					border-radius: 60rpx;
					margin: 10 auto;
					color: #FFFFFF;
					image{
						width: 60rpx;
						height: 60rpx;
						padding-top: 30rpx;
					}
				},
				text{
					font-size:30rpx;
				}
			}
		},
		.hot_goods{
			background: #FFFFFF;
			overflow: hidden;
			.title{
				color: #DC143C;
				height: 50px;
				line-height: 50px;
				margin: 10px 0;
				text-align: center;
				letter-spacing: 20rpx;
				box-shadow: 2px 3px 8px #C0C0C0;
			  },
			.goods_list{
				width: 758rpx;
				position:relative;
				margin-left:0rpx;
				.goods_item{
					position:relative;
					float: right;
					width: 370rpx;
					height:550rpx;
					box-shadow: 1px 2px 3px #C8C7CC;
					margin: 5rpx 0;
					image{
						width: 80%;
						height: 150px;
						padding-left: 30rpx;
					},
					.price{
						padding-top:10rpx;
						color:#DC143C;
						font-size:40rpx;
						margin:20rpx 0 5rpx 0;
						text:nth-child(2){
							color:#eee;
							font-size:28rpx;
							padding-left: 20rpx;
							text-decoration: line-through;
						}
					},
					.font{
						color: #333333;
						font-family: "微软雅黑";
						font-size: 30rpx;
						padding-right: 10rpx;
					}
				}
			}
		}
		}
</style>
