<template>
	<view class="center">
		<view class="bg-info">
			<view class="blance">余额账号（元）</view>
			<view class="money">0.00</view>
		</view>
		<view class="center-list">
			<view class="center-list-item border-bottom">
				<!-- <text class="list-icon">&#xe60f;</text> -->
				<text class="list-text">充值</text>
				<text class="navigat-arrow">&#xe65e;</text>
			</view>
			<view class="center-list-item border-bottom" @tap="goCash">
				<!-- <text class="list-icon">&#xe639;</text> -->
				<text class="list-text">提现</text>
				
				<text class="navigat-arrow">&#xe65e;</text>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				login: true,
				authentication:false,
				avatarUrl: "../../static/logo.png",
				uerInfo: {}
			}
		},
		methods: {
			goCash() {
				uni.navigateTo({
					url:"cash"
				})
			},
			
		},
		onLoad() {
			
		}
	}
</script>

<style>
	@font-face {
		font-family: texticons;
		font-weight: normal;
		font-style: normal;
		src: url('https://at.alicdn.com/t/font_984210_5cs13ndgqsn.ttf') format('truetype');
	}

	page,
	view {
		display: flex;
	}

	page {
		background-color: #f8f8f8;
	}
.bg-info{
	background-color: rgb(27,139,207);
	height: 300upx;
	margin: 10px;
	border-radius: 10px;
	display: inline-block;
	text-align: center;
}
.blance{
	text-align: center;
	color: #FFFFFF;
	padding: 20px 0 0 0;
	display: block;
	
}
.money{
	font-size: 70px;
	color: #FFFFFF;
	text-align: center;
	font-weight: bold;
	display: block;
}
	.center {
		flex-direction: column;
	}

	.logo {
		width: 750upx;
		height: 240upx;
		padding: 20upx;
		box-sizing: border-box;
		flex-direction: row;
		background-color: white;
		align-items: center;
	}

	.logo-hover {
		opacity: 0.8;
	}

	.logo-img {
		width: 150upx;
		height: 150upx;
		border-radius: 150upx;
	}

	.logo-title {
		height: 150upx;
		flex: 1;
		align-items: center;
		justify-content: space-between;
		flex-direction: row;
		margin-left: 20upx;
	}

	.uer-name {
		height: 60upx;
		line-height: 60upx;
		font-size: 38upx;
		color: rgb(36,141,245);
	}

	.go-login.navigat-arrow {
		font-size: 38upx;
		color: #C0C0C0;
	}

	.login-title {
		height: 150upx;
		align-items: self-start;
		justify-content: center;
		flex-direction: column;
		margin-left: 20upx;
	}

	.center-list {
		background-color: #FFFFFF;
		margin-top: 20upx;
		width: 750upx;
		flex-direction: column;
	}

	.center-list-item {
		height: 90upx;
		width: 750upx;
		box-sizing: border-box;
		flex-direction: row;
		padding: 0upx 20upx;
	}

	.border-bottom {
		border-bottom-width: 1upx;
		border-color: #c8c7cc;
		border-bottom-style: solid;
	}

	.list-icon {
		width: 40upx;
		height: 90upx;
		line-height: 90upx;
		font-size: 34upx;
		color: #4cd964;
		text-align: center;
		font-family: texticons;
		margin-right: 20upx;
	}

	.list-text {
		height: 90upx;
		line-height: 90upx;
		font-size: 34upx;
		/*color: #555;*/
		flex: 1;
		text-align: left;
	}
	.text-authen{
		height: 90upx;
		line-height: 90upx;
		font-size: 34upx;
		color: #C0C0C0;
		flex: 0.3;
		
	}
	.navigat-arrow {
		height: 90upx;
		width: 40upx;
		line-height: 90upx;
		font-size: 34upx;
		color: #C0C0C0;
		text-align: right;
		font-family: texticons;
	}
</style>