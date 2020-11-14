<template>
	<view class="community">
		<scroll-view class="left" scroll-y>
			<view :class="active==index?'active':''" 
			@click="avtivehandle(index)"
			v-for="(item,index) in community" 
			:key="item.id">
			{{item.title}}
			</view>			
		</scroll-view>
		
		<scroll-view class="right" scroll-y>
			<view  >
				<image v-for="(item,index) in community_phone" :key="item.id" @click="preImage" :src=item.url></image>
			</view>
		</scroll-view>
	</view>
</template>

<script>
	export default{
		data(){
			return{
				active:0,
				secondData:[],
				community:[
					{title:'摄影设计',id:1},
					{title:'明星美女',id:2},
					{title:'空间设计',id:3},
					{title:'百货超市',id:4},
					{title:'男女内衣',id:5},
					{title:'服装鞋包',id:6},
					{title:'明星写真',id:7},
					{title:'新鲜水果',id:8},
					{title:'杂货零食',id:9},
					{title:'河马生鲜',id:10},
					{title:'性感泳衣',id:11},
					{title:'娱乐空间',id:12},
				],
				community_phone:[
					{url:'../../static/community/design/01.jpg',id:1},
					{url:'../../static/community/design/02.jpeg',id:2},
					{url:'../../static/community/design/03.jpg',id:3},
					{url:'../../static/community/design/04.jpg',id:4}
				]
			}
		},
		methods:{
			avtivehandle(index){
				this.active=index
			}
		}
	}
</script>

<style lang="scss">
	page{
		height: 100%;
	}
	.community{
		height: 100%;
		display: flex;
		.left{
			width: 200rpx;
			height: 100%;
			border-right: 1px solid #eee;
			view{
				height: 60rpx;
				padding: 30rpx 0;
				text-align: center;
				font-size: 30rpx;
				border-top: 1px solid #eee;
			}
			.active{
				background: #DC143C;
				color: #fff;
			}
		}
		.right{
			width:560rpx;
			height:100%;
			mangin:0 auto;
			view{
				image{
					width: 560rpx;
					height: 530rpx;
					border-radius: 5px;
					padding-left: 18rpx;
				}
			}
		}
	}
</style>
