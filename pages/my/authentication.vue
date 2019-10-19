<template>
	
	<view>
		<view class="personal-info">
			<text>个人信息</text>
		</view>
		
		<view class="border-bottom">
		  <view class="title">姓名</view>
		  <view><input class="input-info"  placeholder="真实姓名" /></view>
		</view>
		<view class="border-bottom">
		  <view class="title">身份证号</view>
		  <view><input class="input-info"  placeholder="租赁人身份证号" /></view>
		</view>
		<view class="border-bottom">
		  <view class="title">性别</view>
		  <view><input class="input-info"  placeholder="性别" /></view>
		</view>
		
		<view class="border-bottom">
		  <view class="title">籍贯</view>
		  <view><input class="input-info"  placeholder="身份证所在地" /></view>
		</view>
		<view class="border-bottom">
		  <view class="title">居住地址</view>
		  <view><input class="input-info"  placeholder="现居住地" /></view>
		</view>
		
		<view class="personal-info">
			<text>支付方式</text>
		</view>
		<view class="border-bottom">
		  <view class="title">银行卡</view>
		  <view><input class="input-info"  placeholder="银行卡号码" /></view>
		</view>
		<view class="border-bottom">
		  <view class="title">手机号</view>
		  <view><input class="input-info"  placeholder="银行预留手机号" /></view>
		</view>
		
		<view class="border-bottom">
		  <view class="title-vcode">验证码</view>
		  <view><input class="input-vcode"  placeholder="6位数字" /></view>
		  <view class="send-vcode"><text style="color: #ccc;margin-right: 3px;">|</text> 发送验证码</view>
		</view>
		<button type="primary" style="margin:20px">保存</button>
	</view>
</template>

<script>
</script>

<style>
.personal-info{
	background: rgb(242,242,248);
	height: 80upx;
	
	
}
.personal-info text{
	line-height: 80upx;
	font-size: 14px;
	margin: 0 0 0 20px;
	color: #808080;
}

.title{
	margin: 0 0 0 20px;
	
	width: 240upx;
	line-height: 40px;
	float: left;
}
.title-vcode{
	margin: 0 0 0 20px;
	width: 240upx;
	float: left;
	line-height: 40px;
	
}
.input-info{
	height: 40px;
	width: 110px;
}
.input-vcode{
	width: 115px;
	height: 40px;
	line-height: 40px;
	float: left;
}
.send-vcode{
	height: 40px;
	width: 110px;
	line-height: 40px;
	display: inline-block;
	color: #0081FF;
}
.border-bottom {
	border-bottom-width: 1upx;
	border-color: #c8c7cc;
	border-bottom-style: solid;
}
</style>
