<template>
	<view class="news">
		<view class="news_item" 
		@click="newsClick"
		v-for="(item,index) in news" 
		:key="item.id">
			<image :src=item.image></image>
			<view class="right">
			<view class="title">{{item.title}}</view>
			<view class="info">
				<text>发表时间：2020-11-05  </text>
				<text>浏览：578次</text>
			</view>
			</view>
		</view>
		
	</view>
</template>

<script>
	export default {
		data(){
			return{
				news:[
					{image:'../../static/ask/01.jpg',title:'在娱乐圈中一对模范夫妇，提到陈小春和应采儿了，两个人的爱情...',id:1},
					{image:'../../static/ask/02.png',title:'赵飞燕是汉成帝的第二任皇后，冷艳妖冶，受成帝专宠近十年....',id:2},
					{image:'../../static/ask/03.jpg',title:'偶尔也有失手的时候，这种情况下没有了金箍棒，他会靠着...',id:3},
					{image:'../../static/ask/04.png',title:'这对组合的两个人是一对很好的搭档，虽然他们不是夫妻，但两人...',id:4},
					{image:'../../static/ask/01.jpg',title:'在娱乐圈中一对模范夫妇，提到陈小春和应采儿了，两个人的爱情...',id:5},
					{image:'../../static/ask/02.png',title:'赵飞燕是汉成帝的第二任皇后，冷艳妖冶，受成帝专宠近十年....',id:6},
					{image:'../../static/ask/03.jpg',title:'偶尔也有失手的时候，这种情况下没有了金箍棒，他会靠着...',id:7},
					{image:'../../static/ask/04.png',title:'这对组合的两个人是一对很好的搭档，虽然他们不是夫妻，但两人...',id:8}
				]
			}
		},
		methods:{
			newsClick(){
			uni.navigateTo({
				url:'../news/news'
			})
			}
		}
	}
</script>

<style lang="scss">
	.news{
		.news_item{
			border-bottom: 1px solid #DD524D;
			display: flex;
			padding: 0 10rpx;
			image{
				min-width: 200rpx;
				max-width: 200rpx;
				height: 150rpx;
			}
			.right{
				margin-left: 15rpx;
				display: flex;
				flex-direction: column;
				justify-content: space-between;
			}
			.title{
				font-size: 30rpx;
			}
			.info{
				font-size:24rpx;
				text:nth-child(2){
					padding-left:45rpx;
				}
			}
		}
	}
</style>
