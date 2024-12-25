<template>
	<!-- 轮播图 -->
	<view class="u-wrap">
		<swiper class="swipper-container" circular :indicator-dots="true" :autoplay="true" :interval="2000"
			:duration="true">
			<swiper-item v-for="(item,index) in swipperList">
				<image class="imgs" :src='item.image'></image>
			</swiper-item>
		</swiper>
	</view>
	<!-- 搜索框 -->
	<view class="tab-strickt">
		<u-search bgColor="#f1f4ef" margin="8px" style="flex-grow: 1;" :show-action="false" action-text="搜索"
			:animation="true"></u-search>
	</view>
	<!-- 列表 -->
		<view class="wrap">
		<u-waterfall v-model="flowList" ref="uWaterfall1">
			<template v-slot:left="{leftList}">
				<view class="demo-warter" v-for="(item, index) in leftList" :key="index">
					<!-- 警告：微信小程序中需要hx2.8.11版本才支持在template中结合其他组件，比如下方的lazy-load组件 -->
					<u-lazy-load threshold="-450" border-radius="10" :image="item.image" :index="index"></u-lazy-load>
					<view class="demo-title">
						{{item.title}}
					</view>
					<view class="demo-price">
						{{item.price}}元
					</view>
					<view class="demo-tag">
						<view class="demo-tag-owner">
							自营
						</view>
					</view>
				</view>
			</template>
			<template v-slot:right="{rightList}">
				<view class="demo-warter" v-for="(item, index) in rightList" :key="index">
					<u-lazy-load threshold="-450" border-radius="10" :image="item.image" :index="index"></u-lazy-load>
					<view class="demo-title">
						{{item.title}}
					</view>
					<view class="demo-price">
						{{item.price}}元
					</view>
					<view class="demo-tag">
						<view class="demo-tag-owner">
							自营
						</view>
					</view>
				</view>
			</template>
		</u-waterfall>
		<u-loadmore bg-color="rgb(240, 240, 240)" :status="loadStatus" @loadmore="addRandomData"></u-loadmore>
	</view>
</template>

<script setup>
	import {
		ref
	} from 'vue'
	//轮播图数据
	const swipperList = ref([{
		image: '/static/img1.png'
	}, {
		image: '/static/img2.png'
	}, {
		image: '/static/img3.png'
	}])
	
	//瀑布流数据
	const flowList = ref([{
			price: 75,
			title: '笔记本电脑',
			image: '/static/img1.png',
		},
		{
			price: 385,
			title: '华为手机',
			image: '/static/img1.png',
		},
		{
			price: 784,
			title: '台式电脑',
			image: '/static/img3.png',
		},
		{
			price: 7891,
			title: '电脑',
			image: '/static/img3.png',
		},
		{
			price: 2341,
			title: '自行车',
			image: '/static/img2.png',
		},
		{
			price: 2342,
			title: '考研英语',
			image: '/static/img2.png',
		},
		{
			price: 2341,
			title: '苹果手机',
			image: '/static/img3.png',
		},
		{
			price: 2342,
			title: '小米电视',
			image: '/static/img3.png',
		}
	])
</script>
<style lang="scss" scoped>
   .swipper-container {
   		height: 150px;
   	}
   
   	.imgs {
   		height: 180px;
   		width: 100%;
   	}
   	.demo-warter {
   		border-radius: 8px;
   		margin: 5px;
   		background-color: #ffffff;
   		padding: 8px;
   		position: relative;
   	}
   	
   	.u-close {
   		position: absolute;
   		top: 32rpx;
   		right: 32rpx;
   	}
   	
   	.demo-image {
   		width: 100%;
   		border-radius: 4px;
   	}
   	
   	.demo-title {
   		font-size: 30rpx;
   		margin-top: 5px;
   		color: $u-main-color;
   	}
   	
   	.demo-tag {
   		display: flex;
   		margin-top: 5px;
   	}
   	
   	.demo-tag-owner {
   		background-color: $u-type-error;
   		color: #FFFFFF;
   		display: flex;
   		align-items: center;
   		padding: 4rpx 14rpx;
   		border-radius: 50rpx;
   		font-size: 20rpx;
   		line-height: 1;
   	}
   	
   	.demo-tag-text {
   		border: 1px solid $u-type-primary;
   		color: $u-type-primary;
   		margin-left: 10px;
   		border-radius: 50rpx;
   		line-height: 1;
   		padding: 4rpx 14rpx;
   		display: flex;
   		align-items: center;
   		border-radius: 50rpx;
   		font-size: 20rpx;
   	}
   	
   	.demo-price {
   		font-size: 30rpx;
   		color: $u-type-error;
   		margin-top: 5px;
   	}
   	
   	.demo-shop {
   		font-size: 22rpx;
   		color: $u-tips-color;
   		margin-top: 5px;
   	}
</style>