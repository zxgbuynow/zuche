<template>
	<view class="container">
		
		<tui-tips @tap="gorder" :btnWidth="400" :fixed="false" imgUrl="/static/temp/h1.png" btnText="查看订单信息">
			<view class="title">审核中</view>
			<view class="sub-title">后台工作人员审核中，请耐心等待，稍后客户经理会联系到您，请保持通讯通畅。</view>
		</tui-tips>
	</view>
</template>

<script>
	import tuiTips from "@/components/tips/tips"
	export default {
		components: {
			tuiTips
		},
		data() {
			return {
				show: false
			}
		},
		methods: {
			gorder(){
				uni.switchTab({
					url: '/pages/trade/trade'
				});
				// this.$api.msg('test')
			}
		}
	}
</script>

<style>
	.container {
		padding: 20rpx 0 120rpx 0;
		box-sizing: border-box;
	}

	.header {
		padding: 80rpx 90rpx 60rpx 90rpx;
		box-sizing: border-box;
	}

	.title {
		font-size: 34rpx;
		color: #333;
		font-weight: 500;
	}

	.sub-title {
		font-size: 24rpx;
		color: #7a7a7a;
		padding-top: 18rpx;
	}

	.tui-btn-box {
		padding: 10rpx 40rpx;
		box-sizing: border-box;
	}
	.tui-tips-btn{
		background:#5677fc!important;
	}
</style>
