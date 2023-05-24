<template>
	<view>
		<view v-for="(item,index) in scorearr" :key="index" class="a1">
			<view class="a2">
				<image :src="item.icon" class="a3"></image>
				<view>
					<view class="a4">{{item.title}}</view>
					<view class="a5">讲师:</view>
				</view>
			</view>
			<view class="a6">未发布</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {

			}
		},
		methods: {
			scorearr: [{
					icon: 'https://zhxy-mini.oss-cn-hangzhou.aliyuncs.com/score/3f7f1df2817ae9d6a06ae9458345102.png',
					title: '艺术人体解剖'
				},
				{
					icon: 'https://zhxy-mini.oss-cn-hangzhou.aliyuncs.com/score/3f7f1df2817ae9d6a06ae9458345102.png',
					title: '中国画技法'
				},
				{
					icon: 'https://zhxy-mini.oss-cn-hangzhou.aliyuncs.com/score/3f7f1df2817ae9d6a06ae9458345102.png',
					title: '色彩'
				},
				{
					icon: 'https://zhxy-mini.oss-cn-hangzhou.aliyuncs.com/score/3f7f1df2817ae9d6a06ae9458345102.png',
					title: '书法艺术'
				},
				{
					icon: 'https://zhxy-mini.oss-cn-hangzhou.aliyuncs.com/score/3f7f1df2817ae9d6a06ae9458345102.png',
					title: '艺术美学'
				},
				{
					icon: 'https://zhxy-mini.oss-cn-hangzhou.aliyuncs.com/score/3f7f1df2817ae9d6a06ae9458345102.png',
					title: '素描'
				},
			]
		}
	}
</script>

<style>
	page {
		background-color: #FFFFFF;
	}

	.a1 {
		display: flex;
		flex-direction: row;
		align-items: center;
		padding-left: 30upx;
		padding-right: 30upx;
		margin-top: 20upx;
		background-color: #ffffff;
		justify-content: space-between;
	}

	.a2 {
		display: flex;
		flex-direction: row;
		align-items: center;
	}

	.a3 {
		height: 160upx;
		width: 260upx;
		margin-right: 20upx;
	}

	.a4 {
		font-size: 28upx;
	}

	.a5 {
		font-size: 22upx;
		color: darkgray;
		margin-top: 10upx;
	}

	.a6 {
		background-color: #F3F3F3;
		color: #B0B0B0;
		font-size: 24upx;
		text-align: center;
		height: 50upx;
		line-height: 50upx;
		padding-left: 20upx;
		padding-right: 20upx;
	}
</style>
