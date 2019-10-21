<template>
	<view class="container">
		<tui-sticky :scrollTop="scrollTop" stickyHeight="104rpx">
			<template v-slot:header>
				<view class="sticky-item">
					<view class="date">本月</view>
					<view class="amount">
						<view>合计 ￥5100.00</view>
					</view>
				</view>

			</template>
			<template v-slot:content>
				<!--内容 start-->
				<view class="list-view">
					<view class="list-item" hover-class="hover" :hover-stay-time="150" bindtap="detail">
						<view class="content-box">
							<view class="des-box">
								<view class="tit">租金</view>
								<view class="source">合同编号：xxxx</view>
								<view class="source">车辆信息：沪A12345</view>
								<view class="source">账单号：YS20190506020112341</view>
								<view class="time">支付时间：2019年5月6日 12点59分</view>
							</view>
						</view>
						<view class="money add">
							4900
						</view>
					</view>


					<view class="list-item item-last" hover-class="hover" :hover-stay-time="150" bindtap="detail">
						<view class="content-box">
							<view class="des-box">
								<view class="tit">违章</view>
								<view class="source">合同编号：xxxx</view>
								<view class="source">车辆信息：沪A12345</view>
								<view class="source">账单号：YS20190506020112341</view>
								<view class="time">支付时间：2019年5月6日 12点59分</view>
							</view>
						</view>
						<view class="money add">
							￥200
						</view>
					</view>


				</view>
				<!--内容 end-->
			</template>
		</tui-sticky>


		<tui-sticky :scrollTop="scrollTop" stickyHeight="104rpx">
			<template v-slot:header>
				<view class="sticky-item ">
					<view class="date">9月</view>
					<view class="amount">
						<view>合计 ￥4700.00</view>
					</view>
				</view>
			</template>
			<template v-slot:content>
				<!--内容-->
				<view class="list-view">
					<view class="list-item" hover-class="hover" :hover-stay-time="150" bindtap="detail">
						<view class="content-box">
							<view class="des-box">
								<view class="tit">租金</view>
								<view class="source">合同编号：xxxx</view>
								<view class="source">车辆信息：沪A12345</view>
								<view class="source">账单号：YS20190506020112341</view>
								<view class="time">支付时间：2019年5月6日 12点59分</view>
							</view>
						</view>
						<view class="money add">
							￥4500
						</view>
					</view>
					<view class="list-item item-last" hover-class="hover" :hover-stay-time="150" bindtap="detail">
						<view class="content-box">
							<view class="des-box">
								<view class="tit">违章</view>
								<view class="source">合同编号：xxxx</view>
								<view class="source">车辆信息：沪A12345</view>
								<view class="source">账单号：YS20190506020112341</view>
								<view class="time">支付时间：2019年5月6日 12点59分</view>
							</view>
						</view>
						<view class="money add">
							￥200
						</view>
					</view>

				</view>
				<!--内容-->
			</template>
		</tui-sticky>
		
		<tui-sticky :scrollTop="scrollTop" stickyHeight="104rpx">
			<template v-slot:header>
				<view class="sticky-item ">
					<view class="date">8月</view>
					<view class="amount">
						<view>合计 ￥4600.00</view>
					</view>
				</view>
			</template>
			<template v-slot:content>
				<!--内容-->
				<view class="list-view">
					<view class="list-item" hover-class="hover" :hover-stay-time="150" bindtap="detail">
						<view class="content-box">
							<view class="des-box">
								<view class="tit">租金</view>
								<view class="source">合同编号：xxxx</view>
								<view class="source">车辆信息：沪A12345</view>
								<view class="source">账单号：YS20190506020112341</view>
								<view class="time">支付时间：2019年5月6日 12点59分</view>
							</view>
						</view>
						<view class="money add">
							￥4500
						</view>
					</view>
					<view class="list-item item-last" hover-class="hover" :hover-stay-time="150" bindtap="detail">
						<view class="content-box">
							<view class="des-box">
								<view class="tit">违章</view>
								<view class="source">合同编号：xxxx</view>
								<view class="source">车辆信息：沪A12345</view>
								<view class="source">账单号：YS20190506020112341</view>
								<view class="time">支付时间：2019年5月6日 12点59分</view>
							</view>
						</view>
						<view class="money add">
							￥100
						</view>
					</view>
		
				</view>
				<!--内容-->
			</template>
		</tui-sticky>

	</view>
</template>

<script>
	import tuiSticky from "@/components/sticky/sticky"
	export default {
		components:{
			tuiSticky
		},
		data() {
			return {
				scrollTop: 0
			}
		},
		methods: {
			detail(e) {
				this.tui.toast("详情功能尚未完善~")
			}
		},
		//页面滚动执行方式
		onPageScroll(e) {
			this.scrollTop= e.scrollTop
		}
	}
</script>

<style>
	.container {
		padding-bottom: env(safe-area-inset-bottom);
	}

	.tips {
		background: #fff;
		padding: 50rpx 34rpx;
		color: #555;
		font-size: 24rpx;
		line-height: 42rpx;
		position: relative;
	}

	.tips::before {
		content: '';
		position: absolute;
		border-top: 1rpx solid #eaeef1;
		-webkit-transform: scaleY(0.5);
		transform: scaleY(0.5);
		top: 0;
		right: 0;
		left: 0;
	}

	/* .sticky-container{
 position: relative;
} */
	/* sticky 容器 start */
	.sticky-item {
		width: 100%;
		height: 104rpx;
		padding: 20rpx 30rpx;
		background: #fafafa;
		display: flex;
		align-items: center;
		justify-content: space-between;
		box-sizing: border-box;
	}

	/* sticky 容器 end */

	.date {
		height: 54rpx;
		font-size: 28rpx;
		background: #fff;
		padding: 0 28rpx;
		border-radius: 25rpx;
		display: flex;
		align-items: center;
		justify-content: center;
		position: relative;
		/* box-shadow: 0 0 1rpx #7A7A7A; */
	}

	.date::after {
		content: '';
		position: absolute;
		height: 200%;
		width: 200%;
		border: 1rpx solid #eaeef1;
		border-radius: 60rpx;
		-webkit-transform-origin: 0 0;
		transform-origin: 0 0;
		-webkit-transform: scale(0.5);
		transform: scale(0.5);
		left: 0;
		top: 0;
	}

	.amount {
		text-align: right;
		color: #7A7A7A;
		font-size: 24rpx;
	}

	.list-view {
		position: relative;
		width: 100%;
		overflow: hidden;
	}

	.list-view::after {
		content: '';
		position: absolute;
		border-top: 1rpx solid #eaeef1;
		-webkit-transform: scaleY(0.5);
		transform: scaleY(0.5);
		top: 0;
		right: 0;
		left: 0;
	}

	.list-item {
		width: 100%;
		padding: 30rpx 28rpx;
		box-sizing: border-box;
		background: #fff;
		display: flex;
		align-items: flex-start;
		justify-content: space-between;
	}

	.list-item::after {
		left: 120rpx
	}

	.item-last::after {
		left: 0 !important
	}

	.content-box {
		display: flex;
		align-items: flex-start;
		justify-content: space-between;
	}

	.logo {
		width: 60rpx;
		height: 60rpx;
		flex-grow: 1
	}

	.des-box {
		min-height: 130rpx;
		padding-left: 28rpx;
		box-sizing: border-box;
		vertical-align: top;
		color: #333;
		font-size: 24rpx;
		display: flex;
		flex-direction: column;
		justify-content: space-between;
	}

	.tit {
		font-size: 32rpx;
		max-width: 420rpx;
		white-space: nowrap;
		overflow: hidden;
		text-overflow: ellipsis;
	}

	.time {
		color: #888
	}

	.money {
		font-size: 38rpx;
		font-weight: 500;
		color: #000;
		white-space: nowrap;
		overflow: hidden;
		text-overflow: ellipsis;
		padding-left: 20rpx;
	}

	.add {
		color: #5677FC !important;
	}
</style>
