<template>
	<view>
		<hx-navbar ref="hxnb" :config="config">
			<block slot="left">
				<view class="a1">
					<text class="a2">发现</text>
				</view>
			</block>
		</hx-navbar>
		<view class="a3">
			<image src="https://zhxy-mini.oss-cn-hangzhou.aliyuncs.com/messageicon/fa0de4be8e40bd1b2db53ac96c85cff.png" class="a4"></image>
		</view>
		<l-tabs :list="tabarr" keyName="title" :lineShow="true" :lineCrude="6" :activeSize="18" linePlace="26px"
			activeTextColor="#333" bold=600 textColor="#333" lineColor="linear-gradient(to right, #98F0BC 30%, #98F0BC)"
			@choose="tabChange">
		</l-tabs>
		<swiper :current="tab" class="c6">
			<swiper-item>
				<view class="c7" v-for="(item,index) in noticeArr" :key="index">
					<view class="c8">
						<view class="c9">{{item.title}}</view>
						<view class="d1">{{item.author}}</view>
					</view>
					<image :src="item.icon" class="d2"></image>
				</view>
			</swiper-item>
			<swiper-item>
				<view class="c7" v-for="(item,index) in noticeArr" :key="index">
					<view class="c8">
						<view class="c9">{{item.title}}</view>
						<view class="d1">{{item.author}}</view>
					</view>
					<image :src="item.icon" class="d2"></image>
				</view>
			</swiper-item>
			<swiper-item>
				<view class="c7" v-for="(item,index) in noticeArr" :key="index">
					<view class="c8">
						<view class="c9">{{item.title}}</view>
						<view class="d1">{{item.author}}</view>
					</view>
					<image :src="item.icon" class="d2"></image>
				</view>
			</swiper-item>
			<swiper-item>
				<view class="c7" v-for="(item,index) in noticeArr" :key="index">
					<view class="c8">
						<view class="c9">{{item.title}}</view>
						<view class="d1">{{item.author}}</view>
					</view>
					<image :src="item.icon" class="d2"></image>
				</view>
			</swiper-item>
		</swiper>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				config: {
					back: false,
					fixed: true,
					leftSlot: true,
					search: {
						placeholder: ''
					}
				},
				tabarr: [{
						title: '通知公告'
					},
					{
						title: '学校新闻'
					},
					{
						title: '综合信息'
					},
					{
						title: '学术动态'
					}
				],
				tab: 0,
				noticeArr: [{
						title: '关于加强新生入学后校园安全管理规范的通知',
						author: '校园新闻网',
						icon: 'https://zhxy-mini.oss-cn-hangzhou.aliyuncs.com/20230224095221.png'
					},
					{
						title: '关于开展2019新生入学教育系列培训课程的指导意见',
						author: '信息化管理中心',
						icon: 'https://zhxy-mini.oss-cn-hangzhou.aliyuncs.com/20230224095228.png'
					},
					{
						title: '关于加强新生入学后校园安全管理条例实行的通知',
						author: '教务处',
						icon: 'https://zhxy-mini.oss-cn-hangzhou.aliyuncs.com/20230224095236.png'
					},
					{
						title: '我校举办全国高校廉洁教育大赛，此项赛事是我校首次举办',
						author: '学生处',
						icon: 'https://zhxy-mini.oss-cn-hangzhou.aliyuncs.com/20230224095244.png'
					},
					{
						title: '关于加强新生入学后校园安全管理规范的通知消息',
						author: '校园新闻网',
						icon: 'https://zhxy-mini.oss-cn-hangzhou.aliyuncs.com/20230224095251.png'
					}
				]
			}
		},
		methods: {
			tabChange({
				index,
				item
			}) {
				this.tab = index;
			}
		}
	}
</script>

<style>
page {
		background-color: #FFFFFF;
	}

	.a1 {
		padding-left: 35upx;
	}

	.a2 {
		font-size: 18px;
		font-weight: 700;
	}
	
	.c6 {
		height: 870upx;
	}
	
	.c7 {
		display: flex;
		flex-direction: row;
		align-items: center;
		padding-left: 35upx;
		padding-right: 35upx;
		margin-top: 50upx;
	}
	
	.c8 {
		height: 110upx;
		display: flex;
		flex-direction: column;
		width: 76%;
		padding-right: 30upx;
	}
	
	.c9 {
		font-size: 14px;
		font-weight: 500;
		height: 90upx;
	}
	
	.d1 {
		font-size: 20upx;
		color: #999;
		height: 20upx;
	}
	
	.d2 {
		height: 110upx;
		width: 110upx;
	}
	.a3 {
		display: flex;
		flex-direction: column;
		align-items: center;
		margin-top: 30upx;
		margin-bottom: 50upx;
	}
	
	.a4 {
		height: 300upx;
		width: 92%;
		border-radius: 30upx;
	}
</style>
