<template>
	<view class="container">
		<uni-search-bar @confirm="comfirm1" @input="change" v-model="searchValue"/>
		<!-- <view class="lunbo">
			<swiper :indicator-dots="true" :autoplay="true" :interval="3000" :duration="1000">
				<swiper-item v-for="(item,index) in img" @key="index" class="swiper-item">
					<view > <image :src="item.url" mode="" class="swipImg"></image></view>
					123
				</swiper-item>
			</swiper>
		</view> -->
		<carousel :img-list="img" url-key="url" @selected="selectedBanner"/>
		 
		<scroll-view scroll-x="true" >
			<view class="Ind_select">
				<view class="box">
					<image src="../../static/slide1.jpg" mode=""></image>		
					<view class="span">
						图片采集
					</view>
				</view>
				<view class="box">
					<image src="../../static/slide2.jpg" mode=""></image>
					<view class="span">
						数据录入
					</view>
				</view>
				<view class="box">
					<image src="../../static/slide3.jpg" mode=""></image>
					<view class="span">
						审批
					</view>
				</view>
				<view class="box">
					<image src="../../static/slide4.jpg" mode=""></image>
					<view class="span">
						你猜
					</view>
				</view>
			</view>
		</scroll-view>
		<scroll-view scroll-y="true" >
		<view class="news">
			
		</view>
	</scroll-view>
	</view>
	
</template>

<script>
	import carousel from '../../components/vear-carousel/vear-carousel.vue'
	export default {
		components: {
		  carousel
		},
		data() {
			return {
				href: 'https://uniapp.dcloud.io/component/README?id=uniui',
				searchValue:{},
				img:[{url:"../../static/save1.jpg"},
				{url:"../../static/save2.jpg"},{url:"../../static/save3.jpg"},{url:"../../static/01s.jpg"},
				{url:"../../static/02s.jpg"},{url:"../../static/shuijiao.jpg"}]
			}
		},
		methods: {
			// enter 触发
			comfirm1(){
				console.log(this.searchValue.value,"search")
			},
			// 值变化触发
			change(){
				console.log(this.searchValue.value)
			},
			selectedBanner(item, index) {
			  console.log('🥒', item, index)
			}
		}
	}
</script>

<style lang="less">
	.container {
		padding: 0px 0 50px 0;
		font-size: 14px;
		line-height: 24px;
		// background: #007AFF;
		/* display: flex; */
		.uni-searchbar{
			padding: 8px 8px 0 ;
		}
		.Ind_select{
			width: 1000upx;
			// background: #CCCCCC;
			height: 108upx;
			overflow-x: auto;
			padding: 10upx 0;
			display: flex;
			.box{
				width: 214upx;
				height: 108upx;
				// background: red;
				margin: 0 20upx;
				position: relative;
				image{
					width: 100%;
					height: 108upx;
					opacity: 0.8;
				}
				.span{
					width: 100%;
					height: 100%;
					// background: red;
					color: #fff;
					font-size: 16px;
					line-height: 108upx;
					text-align: center;
					position: absolute;
					top: 0;
				}
			}
		}
		
	}
</style>
