<template>
	<view class="container">
		<image class="img" src="http://cdn.lianxia.top/static/index/首页大字.png" mode=""></image>
		<image class="ip3" src="http://cdn.lianxia.top/static/index/ip形象.gif" mode=""></image>
		<view class="one" @tap="open"></view>
		<view class="two" @tap="turn"></view>
		<uni-popup ref="popup" type="center" :animation="false">
			<view class="indexBackgroud">
				<image class="imgOne" src="http://cdn.lianxia.top/static/index/首页【简介】文字.png" mode=""></image>
			</view>
			<image class="imgTwo" src="http://cdn.lianxia.top/static/index/首页【简介】弹窗关闭按钮.png" mode=""
				@tap.native="close"></image>
		</uni-popup>
	</view>
</template>

<script>
	export default {
		data() {
			return {

			}
		},
		onLoad() {
			// 微信小程序分享功能
			uni.showShareMenu({
				//小程序的原生菜单中显示分享按钮，才能够让发送给朋友与分享到朋友圈两个按钮可以点击
				menus: ["shareAppMessage", "shareTimeline"] //不设置默认发送给朋友
			})
		},
		//发送给朋友
		onShareAppMessage(res) {
			return {
				title: '莲下镇文旅地图',
				path: 'pages/index/index',
				imageUrl: 'http://cdn.lianxia.top/static/分享底图.png' //分享图标，路径可以是本地文件路径、代码包文件路径或者网络图片路径.支持PNG及JPG。显示图片长宽比是 5:4
			}
		},
		//分享到朋友圈
		onShareTimeline(res) {
			return {
				title: '莲下镇文旅地图',
				query: '', //页面参数
				imageUrl: 'http://cdn.lianxia.top/static/分享底图.png' //分享图标，路径可以是本地文件路径、代码包文件路径或者网络图片路径.支持PNG及JPG。显示图片长宽比是 5:4
			}
		},
		methods: {
			open() {
				this.$refs.popup.open();
			},
			close() {
				this.$refs.popup.close();
			},
			turn() {
				uni.navigateTo({
					url: "../video/video"
				})
			}
		}
	}
</script>

<style scoped>
	.container {
		margin: 0 auto;
		position: relative;
		min-height: 100vh;
		background-image: url(http://cdn.lianxia.top/static/index/首页底图.png);
		width: 750rpx;
		background-size: cover;
	}

	.img {
		position: absolute;
		top: 59rpx;
		left: 47rpx;
		width: 570rpx;
		height: 396rpx;
	}

	.ip3 {
		position: absolute;
		top: 110rpx;
		left: 420rpx;
		width: 200rpx;
		height: 200rpx;
	}

	.one {
		position: absolute;
		top: 710rpx;
		left: 323rpx;
		width: 378rpx;
		height: 87rpx;
		background-image: url(http://cdn.lianxia.top/static/index/按钮1.png);
		background-repeat: no-repeat;
		background-size: contain;
	}

	.two {
		position: absolute;
		top: 828rpx;
		left: 323rpx;
		width: 378rpx;
		height: 87rpx;
		background-image: url(http://cdn.lianxia.top/static/index/按钮2.png);
		background-repeat: no-repeat;
		background-size: contain;
	}

	.indexBackgroud {
		position: relative;
		margin-top: 53rpx;
		width: 622rpx;
		height: 1106rpx;
		background-image: url(http://cdn.lianxia.top/static/index/首页【简介】弹窗底图.png);
		background-repeat: no-repeat;
		background-size: contain;
	}

	.imgOne {
		position: absolute;
		left: 50%;
		top: 50%;
		width: 440rpx;
		height: 720rpx;
		margin-left: -220rpx;
		margin-top: -370rpx;
	}

	.imgTwo {
		display: block;
		margin: 2rpx auto;
		width: 60rpx;
		height: 60rpx;
	}
</style>