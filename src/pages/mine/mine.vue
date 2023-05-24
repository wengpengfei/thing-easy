<template>
	<view>
		<hx-navbar ref="hxnb" :config="config">
			<block slot="left">
				<view class="a1">
					<image src="https://zhxy-mini.oss-cn-hangzhou.aliyuncs.com/messageicon/set.png" class="a3" @click="set"></image>
				</view>
			</block>
			<block slot="center">
				<view class="a4">
					我的
				</view>
			</block>
		</hx-navbar>
		<view class="a2">
			<view class="a5">
				<view class="a6">李想</view>
				<view class="a7">信息化管理中心</view>
			</view>
			<image src="https://zhxy-mini.oss-cn-hangzhou.aliyuncs.com/messageicon/%E5%BE%AE%E4%BF%A1%E5%9B%BE%E7%89%87_20230227112548.jpg" class="a8_1"></image>
		</view>
		<view class="a8">
			<image src="https://zhxy-mini.oss-cn-hangzhou.aliyuncs.com/messageicon/ee5acc232805a2ef37bcaa15c89c5e5.png" class="a9"></image>
			<image src="https://zhxy-mini.oss-cn-hangzhou.aliyuncs.com/9b68d524cb40467f2af4578bb774d38.png" class="a9"></image>
		</view>
		<view class="b1">我的待办</view>
		<view class="b3" v-for="(item,index) in messagearr" :key="index">
			<view class="b4">
				<image
					:src="item.icon"
					class="b5"></image>
				<view class="b6">
					<view class="b7">教职工请假申请</view>
					<view class="b8">工作部门：系统维护 请假申请人：</view>
				</view>
			</view>
			<view class="b9">昨天</view>
		</view>
		<view class="b1">我的收藏</view>
		<view class="d3">
			<view class="d4" v-for="(item,index) in newarr" :key="index">
				<image :src="item.icon" class="d5"></image>
				<view class="d6">{{item.title}}</view>
			</view>
		</view>
		<view class="b1">我的信息</view>
		<view class="d3">
			<view class="d4" v-for="(item,index) in arr3" :key="index">
				<image :src="item.icon" class="d5"></image>
				<view class="d6">{{item.title}}</view>
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
					centerSlot:true,
					backgroundColor:[1,['#CEF7E3','#CEF7E3']],
					slideBackgroundColor: [1,['#FFFFFF','#FFFFFF']],
				},
				messagearr:[{
					icon:'https://zhxy-mini.oss-cn-hangzhou.aliyuncs.com/systemicon/f413eab5c055a560c3f7b074121887e.png'
				},{
					icon:'https://zhxy-mini.oss-cn-hangzhou.aliyuncs.com/messageicon/edaefcc8b5dedc0b0f2868675820cb6.png'
				},{
					icon:'https://zhxy-mini.oss-cn-hangzhou.aliyuncs.com/messageicon/f018572d01cc6107ac389eb0a136362.png'
				}],
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
			}
		},
		onPageScroll(e) {
		           // 重点，用到滑动切换必须加上
		           this.$refs.hxnb.pageScroll(e);
		       },
		methods: {
			set(){
				uni.navigateTo({
					url:'/pages/set/set'
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
		background-image: linear-gradient(#CEF7E3,#FFFFFF);
		height: 150upx;
		display: flex;
		flex-direction: row;
		align-items: center;
		justify-content: space-between;
		padding-left: 35upx;
		padding-right: 35upx;
	}
	.a3{
		width: 50upx;height: 50upx;
	}
	.a4{
		margin-left: 220upx;font-size: 34upx;font-weight: 700;
	}
	.a5{
		display: flex;flex-direction: column;
	}
	.a6{
		font-size: 40upx;font-weight: 700;
	}
	.a7{
		font-size: 24upx;color: darkgray;margin-top: 10upx;
	}
	.a8_1{
		height: 100upx;width: 100upx;border-radius: 100%;
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
	.b3 {
		display: flex;
		flex-direction: row;
		align-items: center;
		justify-content: space-between;
		padding-left: 50upx;
		padding-right: 50upx;
		padding-top: 50upx;
	}
	
	.b4 {
		display: flex;
		flex-direction: row;
		align-items: center;
	}
	
	.b5 {
		width: 80upx;
		height: 80upx;
		margin-right: 15upx;
	}
	
	.b6 {
		display: flex;
		flex-direction: column;
	}
	
	.b7 {
		font-size: 28upx;
	}
	
	.b8 {
		font-size: 22upx;
		color: darkgray;
	}
	
	.b9 {
		font-size: 22upx;
		color: darkgray;
	}
	.b1{
		font-size: 32upx;padding-left: 35upx;padding-top: 60upx;font-weight: 600;color: #333;
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
</style>
