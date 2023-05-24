<template>
	<view>
		<hx-navbar ref="hxnb" :config="config">
			<block slot="left">
				<view class="a1">
					<text class="a2">首页</text>
				</view>
			</block>
		</hx-navbar>
		<view class="a3">
			<image src="https://zhxy-mini.oss-cn-hangzhou.aliyuncs.com/4c9c938a2bcc20450f204ed2162f0e7.png" class="a4"></image>
		</view>
		<view class="a5">
			<view class="a6" v-for="(item,index) in navarr" :key="index" @click="navClick(item.page)">
				<image :src="item.icon" class="a7"></image>
				<text>{{item.title}}</text>
			</view>
		</view>
		<view class="a8">
			<image src="https://zhxy-mini.oss-cn-hangzhou.aliyuncs.com/7e794cc8c4698d037e312543da6092a.png" class="a9"></image>
			<image src="https://zhxy-mini.oss-cn-hangzhou.aliyuncs.com/9b68d524cb40467f2af4578bb774d38.png" class="a9"></image>
		</view>
		<view class="b1">
			<view class="b2">
				<image src="../../static/lb_bg.png" class="b3"></image>
				<view>关于系统上线运行的通知</view>
			</view>
			<view class="b4">2-23</view>
		</view>
		<view class="a3">
			<image src="https://zhxy-mini.oss-cn-hangzhou.aliyuncs.com/e241bd1b2938ca35dc99f03da5be9bc.png" class="a4"></image>
		</view>
		<view class="b5">
			<text class="b6">推荐应用</text>
			<text class="b7">根据您最近浏览和办理的应用为您推荐</text>
		</view>
		<view class="b8">
			<view class="b9" v-for="(item,index) in recomarr" :key="index">
				<image :src="item.icon" class="c1"></image>
				<text class="c2">{{item.title}}</text>
				<text class="c3">{{item.value}}</text>
				<text class="c4">{{item.view}}浏览</text>
				<image src="../../static/add.png" class="c5"></image>
			</view>
		</view>
		<!-- tab标签过多 可滚动排列 -->
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
				navarr: [{
						title: '学校概况',
						icon: 'https://zhxy-mini.oss-cn-hangzhou.aliyuncs.com/047dd35c4744b6ed65e465ae33761a6.png',
						page:'/pages/profile/profile'
					},
					{
						title: '成绩查询',
						icon: 'https://zhxy-mini.oss-cn-hangzhou.aliyuncs.com/18e1d86538025f5ca1023196837d9c9.png',
						page:'/pages/score/score'
					},
					{
						title: '网上缴费',
						icon: 'https://zhxy-mini.oss-cn-hangzhou.aliyuncs.com/ff446f254b8809e9c53ba70d3ecf255.png'
					},
					{
						title: '学院预警',
						icon: 'https://zhxy-mini.oss-cn-hangzhou.aliyuncs.com/14488eaf111454f3c39ea4bfce257c9.png'
					},
					{
						title: '全部',
						icon: 'https://zhxy-mini.oss-cn-hangzhou.aliyuncs.com/ceadd80c49f62baaefeaf854770db1f.png'
					}
				],
				recomarr: [{
						title: '成绩查询',
						icon: 'https://zhxy-mini.oss-cn-hangzhou.aliyuncs.com/cec4b314fe7329e364646fb61dfa957.png',
						value: '查询当前及历史成绩',
						view: '200'
					},
					{
						title: '图书借阅',
						icon: 'https://zhxy-mini.oss-cn-hangzhou.aliyuncs.com/eb421804168effaeead7c6c53f1d50a.png',
						value: '查看图书借阅记录',
						view: '200'
					},
					{
						title: '网上缴费',
						icon: 'https://zhxy-mini.oss-cn-hangzhou.aliyuncs.com/c2bebb92244c1752a3236930bd7ea12.png',
						value: '自助网上缴费',
						view: '200'
					}
				],
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
		onLoad() {

		},
		methods: {
			tabChange({
				index,
				item
			}) {
				this.tab = index;
			},
			navClick(page){
				uni.navigateTo({
					url:page
				})
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

	.a3 {
		display: flex;
		flex-direction: column;
		align-items: center;
		margin-top: 30upx;
	}

	.a4 {
		height: 300upx;
		width: 92%;
		border-radius: 30upx;
	}

	.a5 {
		display: flex;
		flex-direction: row;
		align-items: center;
		justify-content: space-around;
		font-size: 22upx;

		color: #666666;
		padding-top: 30upx;
	}

	.a6 {
		display: flex;
		flex-direction: column;
		align-items: center;
	}

	.a7 {
		height: 70upx;
		width: 70upx;
		margin-bottom: 15upx;
	}

	.a8 {
		display: flex;
		flex-direction: row;
		justify-content: space-around;
		margin-top: 40upx;
		padding-left: 20upx;
		padding-right: 20upx;
	}

	.a9 {
		height: 160upx;
		width: 320upx;
		border-radius: 30upx;
	}

	.b1 {
		padding: 50upx 30upx 10upx 30upx;
		display: flex;
		flex-direction: row;
		align-items: center;
		justify-content: space-between;
	}

	.b2 {
		display: flex;
		flex-direction: row;
		align-items: center;
		font-weight: 600;
		font-size: 28upx;
		color: #666666;
	}

	.b3 {
		height: 50upx;
		width: 50upx;
		margin-right: 20upx;
	}

	.b4 {
		font-size: 24upx;
		color: darkgrey;
	}

	.b5 {
		display: flex;
		flex-direction: column;
		padding-left: 30upx;
		margin-top: 30upx;
	}

	.b6 {
		font-size: 18px;
		font-weight: 600;
	}

	.b7 {
		font-size: 20upx;
		color: darkgray;
		margin-top: 10upx;
		letter-spacing: 1upx;
	}

	.b8 {
		display: flex;
		flex-direction: row;
		align-items: center;
		justify-content: space-between;
		padding-top: 70upx;
		padding-left: 30upx;
		padding-right: 30upx;
		margin-bottom: 30upx;
	}

	.b9 {
		display: flex;
		flex-direction: column;
		border-radius: 30upx;
		padding-top: 30upx;
		align-items: center;
		height: 300upx;
		width: 220upx;
		box-shadow: 0px -5px 10px 0px #F3F2F8,
			-6px 0px 6px 0px #F3F2F8,
			6px 0px 6px 0px #F3F2F8,
			0px 5px 19px 0px #F3F2F8;
	}

	.c1 {
		width: 70upx;
		height: 70upx;
	}

	.c2 {
		font-size: 26upx;
		margin-top: 10upx;
	}

	.c3 {
		font-size: 18upx;
		color: darkgray;
	}

	.c4 {
		font-size: 20upx;
		color: #666666;
		margin-top: 20upx;
	}

	.c5 {
		height: 50upx;
		width: 50upx;
		margin-top: 30upx;
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
</style>
