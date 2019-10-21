<template>
	<view class="container">
		<form @submit="formSubmit" @reset="formReset">
			<tui-list-view title="个人信息" unlined="bottom" color="#666" class="tui-list-view">
				<tui-list-cell :hover="false">
					<view class="tui-line-cell">
						<view class="tui-title">姓名</view>
						<input placeholder-class="phcolor" class="tui-input" name="name" placeholder="真实姓名" maxlength="50" type="text" />
					</view>
				</tui-list-cell>
				<tui-list-cell :hover="false">
					<view class="tui-line-cell">
						<view class="tui-title">身份证号码</view>
						<input placeholder-class="phcolor" class="tui-input" name="idcard" placeholder="租赁人身份证号码" maxlength="50" type="text" />
					</view>
				</tui-list-cell>
				<tui-list-cell :hover="false">
					<view class="tui-line-cell">
						<view class="uni-list-cell-left">
							性别
						</view>
						<view class="uni-list-cell-db" style="margin-left: 10px;">
							<picker @change="bindPickerChange" :value="index" :range="array">
								<view class="uni-input" style="color: grey;">{{array[index]}}</view>
							</picker>
						</view>
					</view>
				</tui-list-cell>
				<tui-list-cell :hover="false">
					<view class="tui-line-cell">
						<view class="tui-title">籍贯</view>
						<input placeholder-class="phcolor" class="tui-input" name="birth" placeholder="身份所在地" maxlength="50" type="text" />
					</view>
				</tui-list-cell>
				<tui-list-cell :hover="false">
					<view class="tui-line-cell">
						<view class="tui-title">居住地址</view>
						<input placeholder-class="phcolor" class="tui-input" name="liveaddress" placeholder="现居住地址" maxlength="50" type="text" />
					</view>
				</tui-list-cell>
			</tui-list-view>
			<tui-list-view title="支付方式" unlined="bottom" color="#666" class="tui-list-view">
				<tui-list-cell :hover="false">
					<view class="tui-line-cell">
						<view class="tui-title">银行卡</view>
						<input placeholder-class="phcolor" class="tui-input" name="bank" placeholder="银行卡号码" maxlength="50" type="number" />
					</view>
				</tui-list-cell>
				<tui-list-cell :hover="false">
					<view class="tui-line-cell">
						<view class="tui-title">手机号</view>
						<input placeholder-class="phcolor" class="tui-input" name="mobile" placeholder="银行预留手机号" maxlength="50" type="text" v-model="mobile"/>
					</view>
				</tui-list-cell>
				
				<tui-list-cell :hover="false">
					<view class="tui-line-cell">
						<view class="tui-title">验证码</view>
						<input placeholder-class="phcolor" class="tui-input" name="code" placeholder="6位数字" maxlength="6" type="text" />
						<tui-button size="mini" :type="type" shape="circle" :plain="true" :disabled="disabled" @click="btnSend">{{btnText}}</tui-button>
					</view>
				</tui-list-cell>
			
			</tui-list-view>

			<view class="tui-btn-box">
				<button class="btn-primary" hover-class="btn-hover" formType="submit" type="primary">下一步</button>
			</view>
		</form>
	</view>
</template>
<script>
	const form = require("../../components/utils/formValidation.js")
	import tuiListView from "@/components/list-view/list-view"
	import tuiListCell from "@/components/list-cell/list-cell"
	import tuiButton from "@/components/button/button"
	const util = require('../../utils/util.js')
	export default {
		components: {
			tuiListView,
			tuiListCell,
			tuiButton
		},
		data() {
			return {
				index: 0,
				array: ['男', '女'],
				btnText:'发送校验码',
				mobile: "",
				type: "primary",
				code: "",
				sex:0,
				disabled: false
			}
		},
		methods: {
			formSubmit: function(e) {
				uni.navigateTo({
					url: '/pages/trade/contact'
				});return ;
				//表单规则
				let rules = [{
					name: "name",
					rule: ["required", "isChinese", "minLength:2", "maxLength:6"], //可使用区间，此处主要测试功能
					msg: ["请输入姓名", "姓名必须全部为中文", "姓名必须2个或以上字符", "姓名不能超过6个字符"]
				}, {
					name: "age",
					rule: ["required", "isNum", "range:[0,150]"],
					msg: ["请输入年龄", "请输入正确的年龄", "请输入正确的年龄范围：0-150"]
				}, {
					name: "mobile",
					rule: ["required", "isMobile"],
					msg: ["请输入手机号", "请输入正确的手机号"]
				}, {
					name: "email",
					rule: ["required", "isEmail"],
					msg: ["请输入邮箱", "请输入正确的邮箱"]
				}, {
					name: "idcard",
					rule: ["required", "isIdCard"],
					msg: ["请输入身份证号码", "请输入正确的身份证号码"]
				}, {
					name: "pwd",
					rule: ["required", "isEnAndNo"],
					msg: ["请输入密码", "密码为8~20位数字和字母组合"]
				}, {
					name: "pwd2",
					rule: ["required", "isSame:pwd"],
					msg: ["请输入确认密码", "两次输入的密码不一致"]
				}, {
					name: "range",
					rule: ["required", "range:[3,20]"],
					msg: ["请输入区间数字", "请输入3-20之间的数字"]
				}, {
					name: "amount",
					rule: ["required", "isAmount"],
					msg: ["请输入金额", "请输入正确的金额，允许保留两位小数"]
				}];
				//进行表单检查
				let formData = e.detail.value;
				let checkRes = form.validation(formData, rules);
				if (!checkRes) {
					
					uni.navigateTo({
						url: '/pages/trade/contact'
					})
				} else {
					uni.showToast({
						title: checkRes,
						icon: "none"
					});
				}
			},
			formReset: function(e) {
				console.log("清空数据")
			},
			bindPickerChange: function(e) {
				this.index = e.target.value
			},
			getRandom: function(u) {
				let rnd = "";
				u = u || 6;
				for (var i = 0; i < u; i++) {
					rnd += Math.floor(Math.random() * 10);
				}
				return Number(rnd);
			},
			doLoop: function(seconds) {
				let code = this.getRandom(6);
				this.$api.msg('您本次的验证码是：' + code, 5000);
				console.log(code)
				seconds = seconds ? seconds : 60;
				this.btnText = seconds + "s后获取";
				this.code = code
				let countdown = setInterval(() => {
					if (seconds > 0) {
						this.btnText = seconds + "s后获取"
							--seconds;
					} else {
						this.btnText = "获取验证码";
						this.disabled = false;
						this.type = "primary";
						clearInterval(countdown);
					}
				}, 1000);
			},
			btnSend: function() {
				if (util.isNullOrEmpty(this.mobile)) {
					this.$api.msg('请输入手机号码');
					return
				} else if (!util.isMobile(this.mobile)) {
					this.$api.msg('请输入正确的手机号码');
					return
				}
				this.disabled = true;
				this.btnText = "请稍候...";
				this.type = "gray"
				
				setTimeout(() => {
					this.doLoop(60)
				}, 500)
			}
		}
	}
</script>

<style>
	.container {
		padding: 20rpx 0 50rpx 0;
	}

	.tui-line-cell {
		width: 100%;
		box-sizing: border-box;
		display: flex;
		align-items: center;
	}
	.tui-list-title{
		background-color: #D6D6D6!important;
	}
	.tui-title {
		line-height: 32rpx;
		flex-shrink: 0;
	}

	.tui-input {
		font-size: 32rpx;
		color: #333;
		padding-left: 20rpx;
		flex: 1;
	}

	.radio-group {
		margin-left: auto;
		transform: scale(0.8);
		transform-origin: 100% center;
		flex-shrink: 0;
	}

	.tui-radio {
		display: inline-block;
		padding-left: 28rpx;
		font-size: 36rpx;
		vertical-align: middle;
	}


	.tui-btn-box {
		padding: 40rpx 50rpx;
		box-sizing: border-box;
	}

	.btn-gray {
		margin-top: 30rpx;
	}

	.tui-tips {
		padding: 30rpx;
		color: #999;
		font-size: 24rpx;
	}
</style>
