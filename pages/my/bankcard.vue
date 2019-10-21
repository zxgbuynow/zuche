<template>
	<view>
		<view class="bank-box">
			<view class="left-img left">
				<image class="bank-img" src="../../static/logo.png"></image>
			</view>
			<view class="right-bank right">
				<view class="bank-list">招商银行</view>
				<view class="bank-type">信用卡</view>
				<view class="line"></view>
				<view>**** **** **** 4321</view>
			</view>
			
		</view>
		
		<view class="bank-box">
			<view class="left-img left">
				<image class="bank-img" src="../../static/logo.png"></image>
			</view>
			<view class="right-bank right">
				<view class="bank-list">招商银行</view>
				<view class="bank-type">信用卡</view>
				<view class="line"></view>
				<view>**** **** **** 4321</view>
			</view>
			
		</view>
		
		
		<view class="bank-box">
			<view class="left-img left">
				<image class="bank-img" src="../../static/logo.png"></image>
			</view>
			<view class="right-bank right">
				<view class="bank-list">招商银行</view>
				<view class="bank-type">信用卡</view>
				<view class="line"></view>
				<view>**** **** **** 4321</view>
			</view>
			
		</view>
		
		<button type="primary" style="margin:20px">添加银行卡</button>
	</view>
</template>

<script>
export default {
    data() {
        return{
			text: 'uni-app'
		}
    },
    onLoad: function (options) {
        setTimeout(function () {
            console.log('start pulldown');
        }, 1000);
        uni.startPullDownRefresh();
    },
    onPullDownRefresh() {
        console.log('refresh');
        setTimeout(function () {
            uni.stopPullDownRefresh();
        }, 1000);
    }
}
</script>

<style>
.left{
	float: left;
}
.right{
	float: right;
}
.bank-box{
	border: 1px solid #C0C0C0;
	display: inline-block;
	width: 100%;
	box-shadow: 2px 2px 2px 1px rgba(0, 0, 0, 0.2);
	margin: 0 0 20px 0;
}
.left-img{
	width: 32%;
	margin: 10px 0 0 20px;
	
}
.right-bank{
	width: 60%;
	margin: 10px 0 0 0px;
	
}
.bank-list{
	font-size: 20px;
	
}
.bank-type{
	font-size: 14px;
	
}
.line{
	border-bottom: 1px solid #C0C0C0;
	margin-top: 10upx;
}
.bank-img{
	width: 200upx;
	height: 200upx;
}
</style>
