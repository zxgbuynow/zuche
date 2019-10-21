<template>
	<view class="container">
		
		<tui-tips @tap="gocontact" :btnWidth="400" :fixed="false" imgUrl="/static/temp/h1.png" btnText="获取通讯录信息">
			<view class="title">获取通讯录信息</view>
			<view class="sub-title">点击下发按钮后，系统将会获取你的通讯录信息，系统提示索要权限时，点击确定（通过）即可</view>
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
				show: false,
				list:[]
			}
		},
		methods: {
			gocontact(){
				//获取通讯录
				var that = this  
                // 获取通讯录对象  
                plus.contacts.getAddressBook( plus.contacts.ADDRESSBOOK_PHONE, function( addressbook ) { 
					// uni.showToast({  
					// 	title: '获取通讯录对象成功',  
					// 	duration: 2000  
					// })  
					console.log('获取通讯录对象成功')  
					console.log(JSON.stringify(addressbook)) 
					
					// 查找联系人  
					addressbook.find(["displayName","phoneNumbers"],function(contacts){
							uni.showToast({  
								title: '获取联系人成功',  
								duration: 2000  
							})  
							console.log('获取联系人成功')  
							console.log(JSON.stringify(contacts))  
							that.list = contacts
							uni.navigateTo({
							 	url: '/pages/trade/checkin',
								userdata:contacts
							});
						}, function () {  
							uni.showToast({  
								title: '获取联系人失败',  
								duration: 2000  
							})  
						},{multiple:true});  
					}, function ( e ) {  
						uni.showToast({  
							title: '获取通讯录对象失败:' + e.message,  
							duration: 2000  
						})  
					}); 
				
				
				console.log(JSON.stringify(this.list)) 
				
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
