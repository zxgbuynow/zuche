<template>
	<view class="container">		
		<tui-card :title="card[0].title" :tag="card[0].tag" :header="card[0].header">
			<template v-slot:body>
				<view class="tui-default">
					<text>合同编号：</text>xxxx
				</view>
				<view class="tui-default">
					<text>车辆信息：</text>沪A12345
				</view>
				<view class="tui-default">
					<text>账单号：</text>YS20190506020112341
				</view>
				<view class="tui-default">
					<text>最后缴纳时间：</text>2019年5月6号
				</view>
				<tui-tag size="small" @tap="gopay" type="primary" shape="square" :plain="true" class="tui-right go-pay">去支付</tui-tag>
			</template>
			

		</tui-card>

	</view>
</template>
	
<script>
	import tuiListCell from "@/components/list-cell/list-cell"
	import tuiCard from "@/components/card/card"
	import tuiTag from "@/components/tag/tag"
	export default {
		components: {
			tuiTag,
			tuiListCell,
			tuiCard
		},
		data() {
			return {
				card: [{
						img: {
							url: "/static/images/news/avatar_1.jpg"
						},
						title: {
							text: "租金",
							// color: "#C51A15",
							size: 34
						},
						tag: {
							text: "￥4500",
							color:'#ed3f14'
						},
						header: {
							// bgcolor: "#F7F7F7",
							line: false
						}
					}
				]
			}
		},
		methods: {
			gopay: function() {
				this.$api.msg('功能待完善~')
			},
			
		}
	}
</script>

<style>
	page {
		background: #EDEDED;
	}

	.container {
		padding-bottom: env(safe-area-inset-bottom);
	}
	.tui-card{
		margin-top: 20upx!important;
	}
	.go-pay{
		float: right;
		    border-radius: 0upx!important;
		margin: -60upx 26upx;
	}
	.tui-title {
		width: 100%;
		padding: 70upx 30upx 30upx 30upx;
		box-sizing: border-box;
		font-size: 30upx;
		line-height: 30upx;
		color: #666;
	}

	.tui-default {
		padding: 20upx 30upx;
	}

	.tui-article {
		position: relative;
	}

	.tui-article-img {
		width: 100%;
		height: 300upx;
		display: block;
	}

	.tui-article-title {
		position: absolute;
		left: 0;
		bottom: 0;
		color: #fff;
		font-size: 32upx;
		font-weight: 500;
		box-sizing: border-box;
		padding: 20upx 30upx;
		background: linear-gradient(to bottom, transparent, rgba(0, 0, 0, 0.6));
	}

	.tui-cell-title {
		font-size: 32upx;
		font-weight: 500;
		padding: 0 10upx;
		word-break: break-all;
		word-wrap: break-word;
	}

	.tui-cell-img {
		height: 160upx;
		width: 160upx;
	}

	.tui-flex {
		display: flex;
		align-items: center;
		justify-content: space-between;
	}

	.tui-mr {
		margin-right: 20upx;
	}

	.tui-inline {
		display: inline-block;
	}

	.tui-flex-pic {
		display: flex;
		display: -webkit-flex;
		justify-content: space-between;
		flex-direction: row;
		flex-wrap: wrap;
		box-sizing: border-box;
		background: #fff;
		padding: 0 120upx;
	}

	.tui-flex-pic image {
		width: 32%;
		margin-bottom: 2%;
	}

	.tui-content {
		padding: 0upx 30upx 20upx 120upx;
		box-sizing: border-box;
		font-size: 34upx;
		font-weight: 400;
		color: #333;
	}

	.tui-gray {
		color: #ccc;
	}

	.tui-pleft {
		padding-left: 120upx;
	}
</style>
