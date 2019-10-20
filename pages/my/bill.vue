<template>
	<view>
		<view class="month-info">
			<view class="bg-month"> 
				<text>五月</text>
			</view>
		</view>
		<view class="bill-info">
			<view class="pay-left left">支付</view>
			<view class="money-right right">￥4500</view>
			<view class="origin-info">支付单号：<text>xxxxxxxxxxxxxx</text></view>
			<view class="origin-info">支付方式：<text>招商银行卡(4567)</text></view>
			<view class="origin-info">业务信息：<text>租金应收</text></view>
			<view class="origin-info">成交时间：<text>2019年10月20日17:49:45</text></view>
		</view>
		
		<view class="bill-info">
			<view class="pay-left left">转入</view>
			<view class="money-right right">￥4500</view>
			<view class="origin-info">支付单号：<text>xxxxxxxxxxxxxx</text></view>
			<view class="origin-info">支付方式：<text>招商银行卡(4567)</text></view>
			<view class="origin-info">业务信息：<text>租金应收</text></view>
			<view class="origin-info">成交时间：<text>2019年10月20日17:49:45</text></view>
		</view>
		
		
		<view class="month-info">
			<view class="bg-month"> 
				<text>四月</text>
			</view>
		</view>
		<view class="bill-info">
			<view class="pay-left left">支付</view>
			<view class="money-right right">￥4500</view>
			<view class="origin-info">支付单号：<text>xxxxxxxxxxxxxx</text></view>
			<view class="origin-info">支付方式：<text>招商银行卡(4567)</text></view>
			<view class="origin-info">业务信息：<text>租金应收</text></view>
			<view class="origin-info">成交时间：<text>2019年10月20日17:49:45</text></view>
		</view>
		
		<view class="bill-info">
			<view class="pay-left left">转入</view>
			<view class="money-right right">￥4500</view>
			<view class="origin-info">支付单号：<text>xxxxxxxxxxxxxx</text></view>
			<view class="origin-info">支付方式：<text>招商银行卡(4567)</text></view>
			<view class="origin-info">业务信息：<text>租金应收</text></view>
			<view class="origin-info">成交时间：<text>2019年10月20日17:49:45</text></view>
		</view>
		
		
	</view>
</template>

<script>
</script>

<style>
.left{
	float: left;
}
.right{
	float: right;
}
.bill-info{
	border: 1px solid #FFFFFF;
	box-shadow: 2px 2px 2px 1px rgba(0, 0, 0, 0.2);
	display: inline-block;
	width: 100%;
	
	
}
.pay-left{
	margin: 10px 0 0 20px;
	font-size: 20px;
	
}
.money-right {
	margin: 10px 20px 0 0;
	font-size: 20px;
	
}
.month-info{
	background: rgb(242,242,248);
	height: 80upx;
}
.origin-info{
	clear: both;
	margin: 0 0 0 20px;
	font-size: 14px;
}
.bg-month{
	line-height: 30px;
	margin: 5px 0 0 20px;
	
	width: 60px;
	display: inline-block;
	height: 30px;
	border: 1px solid #FFFFFF;
	background-color: #FFFFFF;
	border-radius: 12upx;
	text-align: center;
	font-size: 14px;
	box-shadow: 2px 2px 2px 1px rgba(0, 0, 0, 0.2);
}

</style>
