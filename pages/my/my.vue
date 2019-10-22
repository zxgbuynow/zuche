<template>
	<view class="center">
		<view class="logo"  :hover-class="!login ? 'logo-hover' : ''">
			<image class="logo-img" :src="uerInfo.avatarUrl ? uerInfo.avatarUrl :avatarUrl"></image>
			<view class="logo-title">
				<text class="uer-name" @click="goLogin">{{login ? uerInfo.name : '登入/注册'}}</text>
				<text style="margin-left: 100px;" v-if="login">￥{{login ? uerInfo.balance :"0.00"}}</text>
				<text class="go-login navigat-arrow" v-if="login">&#xe65e;</text>
			</view>
		</view>
		<view class="center-list">
			<view class="center-list-item border-bottom" @tap="goPerson">
				<!-- <text class="list-icon">&#xe60f;</text> -->
				<text class="list-text">个人信息</text>
				<text class="navigat-arrow">&#xe65e;</text>
			</view>
			<view class="center-list-item border-bottom" @tap="goAuthen">
				<!-- <text class="list-icon">&#xe639;</text> -->
				<text class="list-text">实名认证</text>
				<text class="text-authen">{{!authentication?"未认证":"已认证"}}</text>
				<text class="navigat-arrow">&#xe65e;</text>
			</view>
			<view class="center-list-item border-bottom" @tap="goBankCard">
				<!-- <text class="list-icon">&#xe639;</text> -->
				<text class="list-text">银行卡</text>
				<text class="navigat-arrow">&#xe65e;</text>
			</view>
			<view class="center-list-item border-bottom" @tap="goBill">
				<!-- <text class="list-icon">&#xe639;</text> -->
				<text class="list-text">账单</text>
				<text class="navigat-arrow">&#xe65e;</text>
			</view>
			<view class="center-list-item border-bottom">
				<!-- <text class="list-icon">&#xe639;</text> -->
				<text class="list-text">当前公司</text>
				<text class="navigat-arrow">&#xe65e;</text>
			</view>
		</view>
		<view class="center-list">
			
			<view class="center-list-item border-bottom">
				<!-- <text class="list-icon">&#xe65f;</text> -->
				<text class="list-text">推广</text>
				<text class="navigat-arrow">&#xe65e;</text>
			</view>
		</view>
		<view class="center-list">
			<view class="center-list-item border-bottom">
				<!-- <text class="list-icon">&#xe614;</text> -->
				<text class="list-text">关于</text>
				<text class="navigat-arrow">&#xe65e;</text>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				login: false,
				authentication:false,
				avatarUrl: "../../static/logo.png",
				uerInfo: {}
			}
		},
		onShow() {
			var token  ="";
			var ischeck = '';
			//如果未登录跳转登录
			uni.getStorage({
				key:"token",
				success:function(res){
					if(!res.data) {
						
						uni.navigateTo({
							url:"login"
						})
					}else {
						token = res.data;
					}
				}
			});
			uni.getStorage({
				key:"ischeck",
				success:function(res){
					if(res.data) {
						ischeck = res.data
						
					}
				}
			});
			if(!token) {
				uni.navigateTo({
					url:"login"
				})
				return;
			}
			//if(token) {
				this.login = true;
				//调取myInfo
				uni.request({
					url:this.$url.apiUrl() + "myInfo",
					method:"POST",
					dataType:"json",
					header:{
						token:token,
					},
					success: (res) => {
						if(res.data.status==0) {
							this.uerInfo ={
								"name":res.data.data.username ? res.data.data.username : '测试' ,
								"balance":res.data.data.balance,
								
							}
							if(res.data.data.avatar) {
								this.avatarUrl=res.data.data.avatar;//获取头像
							}
						}
					}
				})
			//}
			if (ischeck) {
				this.authentication = true;
			}
		},
		methods: {
			//个人信息
			goPerson(){
				if (!this.login) {
					uni.navigateTo({
						url:"login"
					});
				}else { //余额
					uni.navigateTo({
						url:"personal"
					})
				}
			},
			//登录
			goLogin() {
				if (!this.login) {
					uni.navigateTo({
						url:"login"
					});
				}else { //余额
					uni.navigateTo({
						url:"balance"
					})
				}
			},
			//实名认证
			goAuthen() {
				if (!this.login) {
					uni.navigateTo({
						url:"login"
					});
					return;
				}
				if(!this.authentication) {
					uni.navigateTo({
						url:"authentication"
					})
				}
			},
			//账单
			goBill() {
				if (!this.login) {
					uni.navigateTo({
						url:"login"
					});
				}else {
					uni.navigateTo({
						url:"bill"
					})
				}
			},
			//银行卡
			goBankCard() {
				if (!this.login) {
					uni.navigateTo({
						url:"login"
					});
				}else {
					uni.navigateTo({
						url:"bankcard"
					})
				}
			}
		},
		onLoad() {
			
			var token = '';
			var ischeck = '';
			uni.getStorage({
				key:"token",
				success:function(res){
					if(res.data) {
						token = res.data
						
					}
				}
			});
			if(!token) {
				console.log(token);
				uni.navigateTo({
					url:"login"
				})
				return;
			}
			uni.getStorage({
				key:"ischeck",
				success:function(res){
					if(res.data) {
						ischeck = res.data
						
					}
				}
			})
			if (token) {
				this.login = true;
				//调取myInfo
				uni.request({
					url:this.$url.apiUrl() + "myInfo",
					method:"POST",
					dataType:"json",
					header:{
						token:token,
					},
					success: (res) => {
						if(res.data.status==0) {
							this.uerInfo ={
								"name":res.data.data.username ? res.data.data.username : '测试' ,
								"balance":res.data.data.balance,
								
							}
							if(res.data.data.avatar) {
								this.avatarUrl=res.data.data.avatar;//获取头像
							}
						}
					}
				})
			}
			if (ischeck) {
				this.authentication = true;
			}
			
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
		/*border-radius: 150upx;*/
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