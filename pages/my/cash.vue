<template>
	<view class="center">
		<view class="bg-info">
			<view class="blance">余额账号（元）</view>
			<view class="money">0.00</view>
		</view>
		<view class="center-list">
			<view class="center-list-item border-bottom">
				<!-- <text class="list-icon">&#xe60f;</text> -->
				<text class="list-text">个人信息</text>
				<text class="navigat-arrow">&#xe65e;</text>
			</view>
		</view>
	</view>
</template>

<script>
</script>

<style>
	@font-face {
		font-family: texticons;
		font-weight: normal;
		font-style: normal;
		src: url('https://at.alicdn.com/t/font_984210_5cs13ndgqsn.ttf') format('truetype');
	}
.center {
		flex-direction: column;
	}
	.center-list {
		background-color: #FFFFFF;
		margin-top: 20upx;
		width: 750upx;
		flex-direction: column;
	}
.bg-info{
	background-color: rgb(27,139,207);
	height: 300upx;
	margin: 10px;
	border-radius: 10px;
}
.blance{
	text-align: center;
	color: #FFFFFF;
	padding: 20px 0 0 0;
}
.money{
	font-size: 80px;
	color: #FFFFFF;
	text-align: center;
	font-weight: bold;
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
