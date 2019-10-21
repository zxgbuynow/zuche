<template>
	<view class="container">
		<tui-tabs :tabs="tabs" :isFixed="scrollTop>=0" :currentTab="currentTab" selectedColor="#E41F19" sliderBgColor=""
		 @change="change"></tui-tabs>
		<!--选项卡逻辑自己实现即可，此处未做处理-->
		<view :class="{'tui-order-list':scrollTop>=0}">
			<view class="tui-order-item" v-for="(model,orderIndex) in 3" :key="orderIndex">
				<block v-for="(item,index) in 2" :key="index">
					<tui-list-cell padding="0" @click="checkout">
						<view class="tui-goods-item">
							<image :src="tmpimg" class="tui-goods-img"></image>
							<view class="tui-goods-center">
								<view class="tui-goods-name">起亚K5</view>
								<view class="tui-goods-attr">三厢|1.4自动|乘坐5人</view>
								<view class="cer-line"></view>
								<view class="tui-goods-attr">以租代购|12期</view>
								<view class="tui-goods-attr">首付xxx元|每期xxx元|总价xxx元</view>
							</view>
							
							
						</view>
					</tui-list-cell>
				</block>
				
			</view>

		</view>
		<!--加载loadding-->
		<tui-loadmore :visible="loadding" :index="3" type="red"></tui-loadmore>
		<tui-nomore :visible="!pullUpOn" bgcolor="#fafafa"></tui-nomore>
		<!--加载loadding-->

	</view>
</template>

<script>
	import tuiTabs from "@/components/tui-tabs/tui-tabs"
	import tuiButton from "@/components/button/button"
	import tuiLoadmore from "@/components/loadmore/loadmore"
	import tuiNomore from "@/components/nomore/nomore"
	import tuiListCell from "@/components/list-cell/list-cell"
	export default {
		components: {
			tuiTabs,
			tuiButton,
			tuiLoadmore,
			tuiNomore,
			tuiListCell
		},
		data() {
			return {
				tabs: [{
					name: "直租"
				}, {
					name: "以租代购"
				}],
				refreshing: false,
				refreshText: '下拉可以刷新',
				currentTab: 0,
				pageIndex: 1,
				loadding: false,
				pullUpOn: true,
				scrollTop: 0,
				tmpimg:'/static/temp/cate1.jpg'
			}
		},
		created() {
			this.getList();
		},
		methods: {
			getList(){
				let activeTab = this.currentTab;
				console.log(activeTab)
			},
			change(e) {
				this.currentTab = e.index
				this.getList();
			},
			checkout(){
				uni.navigateTo({
					url: '/pages/trade/checkout'
				})
				// this.$api.msg("功能尚未完善~")
			}
			
		},
		onPullDownRefresh() {
			setTimeout(() => {
				uni.stopPullDownRefresh()
			}, 200);
		},
		onReachBottom() {
			//只是测试效果，逻辑以实际数据为准
			this.loadding = true
			this.pullUpOn = true
			setTimeout(() => {
				this.loadding = false
				this.pullUpOn = false
			}, 1000)
		},
		onPageScroll(e) {
			this.scrollTop = e.scrollTop;
		}
	}
</script>

<style>
	.container {
		padding-bottom: env(safe-area-inset-bottom);
	}

	.cer-line{
		content: '';
		margin-top: 10rpx;
		border-bottom: 1px solid #eaeef1;
		-webkit-transform: scaleY(0.5);
		-ms-transform: scaleY(0.5);
		transform: scaleY(0.5);
		bottom: 0;
		right: 0;
		left: 0;
	}
	.tui-order-item {
		margin-top: 60rpx;
		border-radius: 10rpx;
		overflow: hidden;
	}

	.tui-goods-title {
		width: 100%;
		font-size: 28rpx;
		display: flex;
		align-items: center;
		justify-content: space-between;
	}
	.tui-goods-status-check, .tui-goods-status-sign, .tui-goods-status-finsh{
		color: #19BE6B;
	}
	.tui-goods-status-fail{
		color: #C51A15;
	}
	.tui-order-status {
		color: #888;
		font-size: 26rpx;
	}

	.tui-goods-item {
		width: 100%;
		padding: 20rpx 30rpx;
		box-sizing: border-box;
		display: flex;
		justify-content: space-between;
	}

	.tui-goods-img {
		width: 180rpx;
		height: 180rpx;
		display: block;
		flex-shrink: 0;
	}

	.tui-goods-center {
		flex: 1;
		padding: 20rpx 8rpx;
		box-sizing: border-box;
	}

	.tui-goods-name {
		max-width: 310rpx;
		word-break: break-all;
		overflow: hidden;
		text-overflow: ellipsis;
		display: -webkit-box;
		-webkit-box-orient: vertical;
		-webkit-line-clamp: 2;
		font-size: 26rpx;
		line-height: 32rpx;
	}

	.tui-goods-attr {
		font-size: 22rpx;
		color: #888888;
		line-height: 32rpx;
		padding-top: 20rpx;
		word-break: break-all;
		overflow: hidden;
		text-overflow: ellipsis;
		display: -webkit-box;
		-webkit-box-orient: vertical;
		-webkit-line-clamp: 2;
	}

	.tui-price-right {
		text-align: right;
		font-size: 24rpx;
		color: #888888;
		line-height: 30rpx;
		padding-top: 20rpx;
	}

	.tui-color-red {
		color: #E41F19;
		padding-right: 30rpx;
	}

	.tui-goods-price {
		width: 100%;
		display: flex;
		align-items: flex-end;
		justify-content: flex-end;
		font-size: 24rpx;
	}

	.tui-size-24 {
		font-size: 24rpx;
		line-height: 24rpx;
	}

	.tui-price-large {
		font-size: 32rpx;
		line-height: 30rpx;
		font-weight: 500;
	}

	.tui-order-btn {
		width: 100%;
		display: flex;
		align-items: center;
		justify-content: flex-end;
		background: #fff;
		padding: 10rpx 30rpx 20rpx;
		box-sizing: border-box;
	}

	.tui-btn-ml {
		margin-left: 20rpx;
		margin-top: 30rpx;
	}
</style>
