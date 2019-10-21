<template>
	<view class="container">
		<tui-list-view title="费用信息" color="#777" class="tui-list-view">
			<tui-list-cell @tap="gopay" :arrow="true" :hover="false" color="#C51A15">
				<text class="tui-list-cell-name">待缴 ￥5000</text>
				<tui-tag size="small" type="light-green" shape="circle" class="tui-right">去缴费</tui-tag>
			</tui-list-cell>
		</tui-list-view>
		
		<tui-list-view title="费用信息" color="#777" class="tui-list-view">
			<tui-list-cell @tap="gorderlist" :arrow="true" :hover="false" color="#C51A15">
				<text class="tui-list-cell-name">无待缴费5/12</text>
				<tui-tag size="small" type="light-green" shape="circle" class="tui-right">查看历史账单</tui-tag>
			</tui-list-cell>
		</tui-list-view>
		
		<tui-list-view title="合同信息" color="#777" class="tui-list-view">
			<tui-list-cell  :hover="false">
				<text class="tui-list-cell-name">合同编号</text>
				<view class="tui-right">HL20190819</view>
			</tui-list-cell>
			<tui-list-cell  :hover="false">
				<text class="tui-list-cell-name">开始时间</text>
				<view class="tui-right">2019年1月1号</view>
			</tui-list-cell>
			<tui-list-cell  :hover="false" :last="false">
				<text class="tui-list-cell-name">结束时间</text>
				<view class="tui-right">2020年1月1号</view>
			</tui-list-cell>
			<tui-list-cell  :hover="false" :last="false">
				<text class="tui-list-cell-name">交车时间</text>
				<view class="tui-right">2019年1月1号</view>
			</tui-list-cell>
			<tui-list-cell  :hover="false" :last="false">
				<text class="tui-list-cell-name">期数</text>
				<view class="tui-right">12</view>
			</tui-list-cell>
			<tui-list-cell  :hover="false" :last="false">
				<text class="tui-list-cell-name">总金额</text>
				<view class="tui-right">200,000元</view>
			</tui-list-cell>
		</tui-list-view>
		<tui-list-view title="车辆信息" color="#777" class="tui-list-view">
			<tui-list-cell  :hover="false">
				<text class="tui-list-cell-name">车牌号</text>
				<view class="tui-right">沪A88888</view>
			</tui-list-cell>
			<tui-list-cell  :hover="false">
				<text class="tui-list-cell-name">车架号</text>
				<view class="tui-right">ABCD1234567890123</view>
			</tui-list-cell>
			<tui-list-cell  :hover="false" :last="false">
				<text class="tui-list-cell-name">发动机号</text>
				<view class="tui-right">A123NHD1</view>
			</tui-list-cell>
			<tui-list-cell  :hover="false" :last="false">
				<text class="tui-list-cell-name">品牌</text>
				<view class="tui-right">起亚</view>
			</tui-list-cell>
			<tui-list-cell  :hover="false" :last="false">
				<text class="tui-list-cell-name">车型</text>
				<view class="tui-right">K2</view>
			</tui-list-cell>
			<tui-list-cell  :hover="false" :last="false">
				<text class="tui-list-cell-name">年款</text>
				<view class="tui-right">2019年运动款</view>
			</tui-list-cell>
		</tui-list-view>
		
		<!--内容部分-->
	</view>
</template>

<script>
	import tuiListView from "@/components/list-view/list-view"
	import tuiListCell from "@/components/list-cell/list-cell"
	import tuiTag from "@/components/tag/tag"
	export default {
		components: {
			tuiTag,
			tuiListView,
			tuiListCell
		},
		data() {
			return {

			}
		},
		methods: {
			gopay: function() {
				uni.navigateTo({
					url: '/pages/trade/pay'
				})
				// uni.showToast({
				// 	title: '详情功能尚未完善~',
				// 	icon: "none"
				// })
			},
			gorderlist:function(){
				uni.navigateTo({
					url: '/pages/trade/list'
				})
			}
		}
	}
</script>

<style>
	.container {
		padding-bottom: env(safe-area-inset-bottom);
	}

	.tui-list-view {
		padding-top: 40upx !important
	}

	.tui-list-cell-name {
		padding-left: 20upx;
		vertical-align: middle;
		line-height: 30upx;
	}

	.tui-list::after {
		left: 94upx !important
	}

	.tui-right {
		margin-left: auto;
		margin-right: 34upx;
		font-size: 26upx;
		line-height: 1;
		color: #999;
	}

	.logo {
		height: 40upx;
		width: 40upx;
	}

	.tui-flex {
		display: flex;
		align-items: center;
	}

	.tui-msg-box {
		display: flex;
		align-items: center;
	}

	.tui-msg-pic {
		width: 100upx;
		height: 100upx;
		border-radius: 50%;
		display: block;
		margin-right: 24upx;
	}

	.tui-msg-item {
		max-width: 500upx;
		min-height: 80upx;
		overflow: hidden;
		display: flex;
		flex-direction: column;
		justify-content: space-between;
	}

	.tui-msg-name {
		overflow: hidden;
		white-space: nowrap;
		text-overflow: ellipsis;
		font-size: 34upx;
		line-height: 1;
		color: #262b3a;
	}

	.tui-msg-content {
		overflow: hidden;
		white-space: nowrap;
		text-overflow: ellipsis;
		font-size: 26upx;
		line-height: 1;
		color: #9397a4;
	}

	.tui-msg-right {
		max-width: 120upx;
		height: 88upx;
		margin-left: auto;
		text-align: right;
		display: flex;
		flex-direction: column;
		justify-content: space-between;
		align-items: flex-end;
	}

	.tui-msg-right.tui-right-dot {
		height: 76upx;
		padding-bottom: 10upx;

	}

	.tui-msg-time {
		width: 100%;
		font-size: 24upx;
		line-height: 24upx;
		color: #9397a4;
	}

	.tui-badge {
		width: auto
	}

	.tui-msg::after {
		left: 154upx !important
	}
</style>
