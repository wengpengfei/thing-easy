<template>
	<view>
		<hx-navbar ref="hxnb" :config="config">
		</hx-navbar>
		<view class="a1">
			<image src="https://zhxy-mini.oss-cn-hangzhou.aliyuncs.com/profile/1629099393846928.jpg" class="a2"></image>
		</view>
		<l-tabs :list="tabarr" keyName="title" :lineShow="true" :lineCrude="6" :activeSize="18" linePlace="26px"
			activeTextColor="#333" bold=600 textColor="#333" lineColor="linear-gradient(to right, #98F0BC 30%, #98F0BC)"
			@choose="tabChange">
		</l-tabs>
		<swiper style="height: 1500upx;">
			<swiper-item>
				<view class="a3">
					青岛黄海学院创建于1996年，是教育部批准的普通本科高校。学校设有国际商学院、智能制造学院、建筑工程学院、艺术学院、学前教育学院、护理与健康学院、大数据学院、经济管理学院、马克思主义学院、创新创业教育学院、国学院、继续教育中心、大学体育教学部等13个教学单位。开设70余个本专科专业，涵盖工学、管理学、经济学、教育学、艺术学、医学、文学等学科门类。学校占地面积1720亩，建筑面积85.69万平方米，现有全日制在校生30000余人，教职工1726人。办学26年来，为社会培养了15万余名高素质应用型人才。
				</view>
				<view class="a4">党建引领  健康发展</view>
				<view class="a3">学校全面贯彻党的教育方针，坚持社会主义办学方向。学校党委坚持围绕中心抓党建、抓好党建促发展的理念，扎实开展了党的群众路线、三严三实、“不忘初心 牢记使命”主题教育。2016年在全省民办高校党建培训班介绍经验；2018年成立马克思主义学院，成为山东省首家成立马克思主义学院的民办高校，首批获评山东省社会科学重点研究基地的民办高校，民办高校第一家山东省示范思想政治教学部；2019年艺术学院教师党支部获评“全国党建工作样板支部”、智能制造学院党总支获评“山东党建工作标杆院系”，马克思主义学院党支部获评“山东省先进基层党组织”“山东党建工作样板支部”“山东教育系统先进基层党组织”。</view>
			</swiper-item>
		</swiper>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				config: {
					fixed: true,
					title:'青岛黄海学院',
					backgroundColor:[1,['#CEF7E3','#CEF7E3']],
					slideBackgroundColor: [1,['#FFFFFF','#FFFFFF']],
				},
				tab:0,
				tabarr: [{
						title: '学校简介'
					},
					{
						title: '办学理念'
					},
					{
						title: '学校沿革'
					},
					{
						title: '组织机构'
					}
				],
			}
		},
		methods: {
			tabChange({
				index,
				item
			}) {
				this.tab = index;
			},
		}
	}
</script>

<style>
	
	.a1 {
		background-image: linear-gradient(#CEF7E3,#FFFFFF);
		height: 350upx;
		display: flex;
		flex-direction: column;
		align-items: center;
	}
	.a2{
		height: 300upx;margin-top: 30upx;border-radius: 30upx;width: 96%;
	}
	.a3{
		text-indent: 50upx;padding-left: 40upx;padding-right: 40upx;font-size: 30upx;
	}
	.a4{
		padding-left: 40upx;padding-top: 50upx;font-size: 40upx;padding-bottom: 50upx;
	}
</style>
