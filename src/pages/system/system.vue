<template>
	<view>
		<hx-navbar ref="hxnb" :config="config">
			<block slot="left">
				<view class="a1">
					<text class="a2">应用</text>
				</view>
			</block>
		</hx-navbar>
		<view class="a8">
			<image src="https://zhxy-mini.oss-cn-hangzhou.aliyuncs.com/7e794cc8c4698d037e312543da6092a.png" class="a9">
			</image>
			<image src="https://zhxy-mini.oss-cn-hangzhou.aliyuncs.com/9b68d524cb40467f2af4578bb774d38.png" class="a9">
			</image>
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
		<l-tabs :list="tabarr" keyName="title" :lineShow="true" :lineCrude="6" :activeSize="18" linePlace="26px"
			activeTextColor="#333" bold=600 textColor="#333" lineColor="linear-gradient(to right, #98F0BC 30%, #98F0BC)"
			@choose="tabChange">
		</l-tabs>
		<view class="d1">
			<view class="d2" id="a1">最新上线</view>
			<view class="d3">
				<view class="d4" v-for="(item,index) in newarr" :key="index">
					<image :src="item.icon" class="d5"></image>
					<view class="d6">{{item.title}}</view>
				</view>
			</view>
			<view class="d7" id="a2">电子教务</view>
			<view class="d3">
				<view class="d4" v-for="(item,index) in arr2" :key="index">
					<image :src="item.icon" class="d5"></image>
					<view class="d6">{{item.title}}</view>
				</view>
			</view>
			<view class="d7" id="a3">教学服务</view>
			<view class="d3">
				<view class="d4" v-for="(item,index) in arr3" :key="index">
					<image :src="item.icon" class="d5"></image>
					<view class="d6">{{item.title}}</view>
				</view>
			</view>
			<view class="d7" id="a4">科研服务</view>
			<view class="d3">
				<view class="d4" v-for="(item,index) in arr4" :key="index">
					<image :src="item.icon" class="d5"></image>
					<view class="d6">{{item.title}}</view>
				</view>
			</view>
		</view>
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
						title: '最新上线'
					},
					{
						title: '电子教务'
					},
					{
						title: '教学服务'
					},
					{
						title: '科研服务'
					}
				],
				tab: 0,
				newarr:[{
					title:'学校概况',
					icon:'https://zhxy-mini.oss-cn-hangzhou.aliyuncs.com/systemicon/936f56ba2907dd1b38e0afa3c8b0937.png'
				},
				{
					title:'校园地图',
					icon:'https://zhxy-mini.oss-cn-hangzhou.aliyuncs.com/systemicon/f5caf4acfc9228f8ac87423da52dc2e.png'
				},
				{
					title:'我的消费',
					icon:'https://zhxy-mini.oss-cn-hangzhou.aliyuncs.com/systemicon/1a511be1539543c4fefbebfe9b876dc.png'
				},
				{
					title:'电子邮件',
					icon:'https://zhxy-mini.oss-cn-hangzhou.aliyuncs.com/systemicon/cdf30ec3d1e45163d4c2073ae6104ef.png'
				},{
					title:'图书借阅',
					icon:'https://zhxy-mini.oss-cn-hangzhou.aliyuncs.com/systemicon/eb9e2b0ca4763bd9f6a85ad76883534.png'
				},{
					title:'获奖成果',
					icon:'https://zhxy-mini.oss-cn-hangzhou.aliyuncs.com/systemicon/4b55743d16e4d5fac816b565fe82cef.png'
				},{
					title:'我的党建',
					icon:'https://zhxy-mini.oss-cn-hangzhou.aliyuncs.com/systemicon/bb7915c10196a8c55fd8502bf80aeb4.png'
				},{
					title:'网上审批',
					icon:'https://zhxy-mini.oss-cn-hangzhou.aliyuncs.com/systemicon/6f0df4c8b0619a873494f88d523f3f1.png'
				}],
				arr2:[{
					title:'网上审批',
					icon:'https://zhxy-mini.oss-cn-hangzhou.aliyuncs.com/systemicon/6f0df4c8b0619a873494f88d523f3f1.png'
				},
				{
					title:'成绩查询',
					icon:'https://zhxy-mini.oss-cn-hangzhou.aliyuncs.com/systemicon/7cb99c4ec406648b4f50d650ee724a3.png'
				},
				{
					title:'网上缴费',
					icon:'https://zhxy-mini.oss-cn-hangzhou.aliyuncs.com/systemicon/804f97787e3257c342356777753d4e3.png'
				},
				{
					title:'学院预警',
					icon:'https://zhxy-mini.oss-cn-hangzhou.aliyuncs.com/systemicon/33d70d929a4526ad17e28e488a9980f.png'
				},{
					title:'办事指南',
					icon:'https://zhxy-mini.oss-cn-hangzhou.aliyuncs.com/systemicon/bec6314f3a8f265a37e8db370fd06b0.png'
				}],
				arr3:[{
					title:'图书借阅',
					icon:'https://zhxy-mini.oss-cn-hangzhou.aliyuncs.com/systemicon/eb9e2b0ca4763bd9f6a85ad76883534.png'
				},
				{
					title:'课堂考勤',
					icon:'https://zhxy-mini.oss-cn-hangzhou.aliyuncs.com/systemicon/d0c5d022fae2cee3fda8ac7cd9d102a.png'
				},
				{
					title:'练习中心',
					icon:'https://zhxy-mini.oss-cn-hangzhou.aliyuncs.com/systemicon/377d1383186d195b2ba0592eeb6f0ec.png'
				},
				{
					title:'综合实践',
					icon:'https://zhxy-mini.oss-cn-hangzhou.aliyuncs.com/systemicon/c2ed9a527a79db77f1e89feb74e5731.png'
				},{
					title:'选课排课',
					icon:'https://zhxy-mini.oss-cn-hangzhou.aliyuncs.com/systemicon/19d4cbe79e9e58a1c46368f15232fba.png'
				},{
					title:'课表查询',
					icon:'https://zhxy-mini.oss-cn-hangzhou.aliyuncs.com/systemicon/a17bc786a4f58980b6e03f7de5152f6.png'
				}],
				arr4:[{
					title:'获奖成果',
					icon:'https://zhxy-mini.oss-cn-hangzhou.aliyuncs.com/systemicon/4b55743d16e4d5fac816b565fe82cef.png'
				},
				{
					title:'研究课题',
					icon:'https://zhxy-mini.oss-cn-hangzhou.aliyuncs.com/systemicon/e2133193c16cf3c0a5ca93dd4a31f26.png'
				}]
			}
		},
		methods: {
			tabChange({
				index,
				item
			}) {
				this.getElementScollTop("a"+(index+1))
			},
			 //获取元素离页面顶部的距离
			getElementScollTop(element) {
			    const query = uni.createSelectorQuery()
				console.log(element)
			    query.select('#'+element).boundingClientRect((data) => {
			        let pageScrollTop = Math.round(data.top)
			        uni.pageScrollTo({
			            scrollTop: pageScrollTop-400, //滚动的距离
			            duration: 0, //过渡时间
			        })
			      }).exec()
			    },

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

	.d1 {
		
		margin-top: 30upx;
		
	}

	.d2 {
		padding-right: 40upx;
		padding-left: 40upx;
		font-weight: 600;
		font-size: 26upx;
		color: #333;
		margin-top: 30upx;
	}

	.d3 {
		display: flex;
		flex-direction: row;
		flex-wrap: wrap;
	}


	.d4 {
		display: flex;
		flex-direction: column;
		align-items: center;
		width: 25%;
		margin-top: 30upx;
	}

	.d5 {
		height: 60upx;
		width: 60upx;
	}

	.d6 {
		font-size: 22upx;
		margin-top: 15upx;
	}
	.d7{
		
			padding-right: 40upx;
			padding-left: 40upx;
			font-weight: 600;
			font-size: 26upx;
			margin-top: 50upx;
			color: #333;
		
	}
</style>
