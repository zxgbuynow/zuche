<template>
	<view>
		<view class="p-info"> 
			<image class="header-img" src="../../static/logo.png"></image>
		</view>
		<view class="text-info" @tap="updateInfo('fullname')">
			<view class="title-small">姓名</view>
			<view class="content-info">张三</view>
		</view>
		<view class="text-info" @tap="updateInfo('mobile')">
			<view class="title-small">手机号</view>
			<view class="content-info">132****1234</view>
		</view>
		<view class="text-info" @tap="updateInfo('email')">
			<view class="title-small">邮箱</view>
			<view class="content-info">未填写</view>
		</view>
		<button type="default" style="margin:50px 20px 0 20px">退出登入</button>
	</view>
</template>

<script>
export default {
	data(){
		return{
			
		}
	},
	methods:{
		updateInfo(type){
			this.$api.msg(type);
		}
	},
	onLoad() {
		
	}
}
</script>

<style>
.p-info{
	height: 200px;
	background-color: rgb(242,242,248);
	text-align: center;
	border-bottom: 1px solid #C0C0C0;
}
.header-img{
	width: 150upx;
	height: 150upx;
	margin: 60px 0 0 0;
}
.text-info{
	border-bottom: 1px solid #C0C0C0;
	
}
.title-small{
	font-size: 16px;
	margin: 10px 0 0 20px;
	color: #C0C0C0;
	
}
.content-info{
	margin: 5px 0 0 20px;
	font-size: 18px;
}
</style>
