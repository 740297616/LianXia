<template>
	<view class="picPreview">
		<movable-area scale-area>
			<movable-view direction="all" @scale="onScale" scale="true" scale-min="2.65" scale-max="5"
				:scale-value="scaleValue" x="-500" y="-820" animation="false">
				<image :src="previewUrl" mode="widthFix">
					<view @tap="open(23)"
						style="position:absolute; top:1560rpx; left:3670rpx; width:690rpx; height:120rpx;  background: url(http://cdn.lianxia.top/static/shop/阿沛牛肉火锅.png) top/contain no-repeat;font-size:0px;">
					</view>
					<view @tap="open(22)"
						style="position:absolute; top:1400rpx; left:6210rpx; width:610rpx; height:120rpx;  background: url(http://cdn.lianxia.top/static/shop/荔园大排档.png) top/contain no-repeat;font-size:0px;">
					</view>
					<view @tap="open(4)"
						style="position:absolute; top:1810rpx; left:6260rpx; width:460rpx; height:120rpx;  background: url(http://cdn.lianxia.top/static/shop/百家宴.png) top/contain no-repeat;font-size:0px;">
					</view>
					<view @tap="open(10)"
						style="position:absolute; top:1970rpx; left:6230rpx; width:530rpx; height:120rpx;  background: url(http://cdn.lianxia.top/static/shop/花餐字号.png) top/contain no-repeat;font-size:0px;">
					</view>
					<view @tap="open(9)"
						style="position:absolute; top:2140rpx; left:4910rpx; width:360rpx; height:120rpx;  background: url(http://cdn.lianxia.top/static/shop/芋匠.png) top/contain no-repeat;font-size:0px;">
					</view>
					<view @tap="open(21)"
						style="position:absolute; top:2250rpx; left:5020rpx; width:780rpx; height:120rpx;  background: url(http://cdn.lianxia.top/static/shop/老戏院前鸭肉饭.png) top/contain no-repeat;font-size:0px;">
					</view>
					<view @tap="open(12)"
						style="position:absolute; top:2380rpx; left:5600rpx; width:530rpx; height:120rpx;  background: url(http://cdn.lianxia.top/static/shop/北巷寿司.png) top/contain no-repeat;font-size:0px;">
					</view>
					<view @tap="open(16)"
						style="position:absolute; top:2480rpx; left:5660rpx; width:530rpx; height:120rpx;  background: url(http://cdn.lianxia.top/static/shop/北食干锅.png) top/contain no-repeat;font-size:0px;">
					</view>
					<view @tap="open(3)"
						style="position:absolute; top:2700rpx; left:3810rpx; width:610rpx; height:120rpx;  background: url(http://cdn.lianxia.top/static/shop/逢源鹧鸪饭.png) top/contain no-repeat;font-size:0px;">
					</view>
					<view @tap="open(17)"
						style="position:absolute; top:3190rpx; left:4150rpx; width:610rpx; height:120rpx;  background: url(http://cdn.lianxia.top/static/shop/商贸城炸鸡.png) top/contain no-repeat;font-size:0px;">
					</view>
					<view @tap="open(13)"
						style="position:absolute; top:2800rpx; left:6100rpx; width:690rpx; height:120rpx;  background: url(http://cdn.lianxia.top/static/shop/欣记鹅肠火锅.png) top/contain no-repeat;font-size:0px;">
					</view>
					<view @tap="open(11)"
						style="position:absolute; top:2910rpx; left:5980rpx; width:690rpx; height:120rpx;  background: url(http://cdn.lianxia.top/static/shop/澄鹅卤鹅饭店.png) top/contain no-repeat;font-size:0px;">
					</view>
					<view @tap="open(8)"
						style="position:absolute; top:3020rpx; left:5680rpx; width:530rpx; height:120rpx;  background: url(http://cdn.lianxia.top/static/shop/食之有味.png) top/contain no-repeat;font-size:0px;">
					</view>
					<view @tap="open(5)"
						style="position:absolute; top:3150rpx; left:5260rpx; width:530rpx; height:120rpx;  background: url(http://cdn.lianxia.top/static/shop/潮香小炒.png) top/contain no-repeat;font-size:0px;">
					</view>
					<view @tap="open(18)"
						style="position:absolute; top:3250rpx; left:5510rpx; width:530rpx; height:120rpx;  background: url(http://cdn.lianxia.top/static/shop/巷内撸串.png) top/contain no-repeat;font-size:0px;">
					</view>
					<view @tap="open(6)"
						style="position:absolute; top:3350rpx; left:5100rpx; width:840rpx; height:120rpx;  background: url(http://cdn.lianxia.top/static/shop/老椰吉海南清凉补.png) top/contain no-repeat;font-size:0px;">
					</view>
					<view @tap="open(1)"
						style="position:absolute; top:3580rpx; left:4830rpx; width:530rpx; height:120rpx;  background: url(http://cdn.lianxia.top/static/shop/阿深冷饮.png) top/contain no-repeat;font-size:0px;">
					</view>
					<view @tap="open(20)"
						style="position:absolute; top:3500rpx; left:5400rpx; width:680rpx; height:120rpx;  background: url(http://cdn.lianxia.top/static/shop/老牌英博烧烤.png) top/contain no-repeat;font-size:0px;">
					</view>
					<view @tap="open(14)"
						style="position:absolute; top:3610rpx; left:5310rpx; width:680rpx; height:120rpx;  background: url(http://cdn.lianxia.top/static/shop/林胜彬酸菜鱼.png) top/contain no-repeat;font-size:0px;">
					</view>
					<view @tap="open(7)"
						style="position:absolute; top:3730rpx; left:5270rpx; width:530rpx; height:120rpx;  background: url(http://cdn.lianxia.top/static/shop/頭记冰室.png) top/contain no-repeat;font-size:0px;">
					</view>
					<view @tap="open(2)"
						style="position:absolute; top:3750rpx; left:4490rpx; width:870rpx; height:120rpx;  background: url(http://cdn.lianxia.top/static/shop/彭伯顿.png) top/contain no-repeat;font-size:0px;">
					</view>
					<view @tap="open(25)"
						style="position:absolute; top:3790rpx; left:5810rpx; width:530rpx; height:120rpx;  background: url(http://cdn.lianxia.top/static/shop/清风小院.png) top/contain no-repeat;font-size:0px;">
					</view>
					<view @tap="open(24)"
						style="position:absolute; top:3910rpx; left:5770rpx; width:870rpx; height:120rpx;  background: url(http://cdn.lianxia.top/static/shop/石锅宴.png) top/contain no-repeat;font-size:0px;">
					</view>
					<view @tap="open(19)"
						style="position:absolute; top:4160rpx; left:5330rpx; width:530rpx; height:120rpx;  background: url(http://cdn.lianxia.top/static/shop/啊锋烧烤.png) top/contain no-repeat;font-size:0px;">
					</view>
					<view @tap="open(26)"
						style="position:absolute; top:4090rpx; left:5960rpx; width:680rpx; height:120rpx;  background: url(http://cdn.lianxia.top/static/shop/阿润海鲜排挡.png) top/contain no-repeat;font-size:0px;">
					</view>
					<view @tap="open(15)"
						style="position:absolute; top:4410rpx; left:3600rpx; width:530rpx; height:120rpx;  background: url(http://cdn.lianxia.top/static/shop/神州小炒.png) top/contain no-repeat;font-size:0px;">
					</view>
				</image>
			</movable-view>
		</movable-area>
		<image class="bottom" src="http://cdn.lianxia.top/static/tourism/浮层固定字.png" alt="" />
		<image class="top" src="http://cdn.lianxia.top/static/tourism/浮层固定指南针.png" alt="" />
		<view>
			<uni-popup ref="popup" type="center" :animation="false">
				<view class="popupBack">
					<image src="http://cdn.lianxia.top/static/food/弹窗关闭图标.png" @tap="close"
						style="position: absolute; top:-16rpx;z-index: 3; right:24rpx; width: 56rpx; height: 56rpx;">
					</image>
					<scroll-view scroll-y="true" style="width: 652rpx; height: 974rpx;">
						<view class="pHeader">
							<view
								style="margin-top: 45rpx; background-color: #ffea98; width: 16rpx; height: 16rpx; border-radius: 8rpx;">
							</view>
							<view class="headText" ref="myElement">{{ shopName }}</view>
							<view
								style="margin-top: 45rpx; background-color: #ffea98; width: 16rpx; height: 16rpx; border-radius: 8rpx;">
							</view>
						</view>
						<view style="position: relative; width: 504rpx; height: 337rpx;margin:0 auto ;">
							<cc-mySwiper :swiperArr="imgList"></cc-mySwiper>
							<image src="http://cdn.lianxia.top/static/shop/地图弹窗【美食商家】浮层贴纸.png" mode="heightFix"
								style="display: block; position: absolute; top:-23rpx; left: -33rpx; height: 90rpx; width: 133rpx;">
							</image>
							<image src="http://cdn.lianxia.top/static/shop/地图弹窗【美食商家】浮层贴纸2.png" mode="heightFix"
								style="display: block; position: absolute; bottom:-23rpx; right: -33rpx; height: 90rpx;">
							</image>
						</view>
						<view
							style="margin: 0 auto; margin-top: 40rpx; width: 510rpx; font-size: 30rpx; font-weight: 500; line-height: 47rpx;"
							v-html="shopText"></view>
						<view class="footerLocation" @tap="openLoca">
							<view
								style="display: inline; margin: 20rpx 0; width: 410rpx; font-size: 30rpx; font-weight: 500; line-height:42rpx;"
								v-html="shopLocation"></view>
							<image src="http://cdn.lianxia.top/static/tourism/地图弹窗【地址】导航图标.png"
								style="margin: 20rpx 0; width: 80rpx; height: 80rpx;"></image>
						</view>
						<view v-show="isShow"
							style="margin-right: 70rpx; height: 30rpx; line-height: 30rpx; text-align: right; font-size: 25rpx; color: rgba(0,0,0,0.7);">
							{{ imgFrom }}
						</view>
					</scroll-view>
				</view>
			</uni-popup>
		</view>
	</view>
</template>
<script>
	import shopjson from '../../static/json/shop.json'
	export default {
		data() {
			return {
				shopSrc: '',
				shopName: '',
				imgList: [],
				shopText: "",
				shopaArray: shopjson,
				shopLat: 1,
				shopLng: 1,
				imgFrom: "",
				showPicPreview: true,
				scaleValue: 3,
				previewUrl: "http://cdn.lianxia.top/static/tourism/地图1.0 （文旅）底图.png",
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
		computed: {
			isShow() {
				if (this.imgFrom.length === 0) return false
				else return true
			}
		},
		methods: {
			onScale() {},
			open(id) {
				this.shopName = this.shopaArray[id - 1].Name
				this.imgList = this.shopaArray[id - 1].imglist
				this.shopText = this.shopaArray[id - 1].Introduction
				this.shopLocation = this.shopaArray[id - 1].Address
				this.shopLat = this.shopaArray[id - 1].lat
				this.shopLng = this.shopaArray[id - 1].lng
				this.imgFrom = this.shopaArray[id - 1].from
				this.$refs.popup.open('center')
			},
			close() {
				this.$refs.popup.close()
			},
			openLoca() {
				uni.openLocation({
					latitude: Number(this.shopLng),
					longitude: Number(this.shopLat),
					name: this.shopName,
					address: this.shopLocation,
					success() {
						console.log('success');
					}
				})
			}
		}
	}
</script>

<style lang="scss" scoped>
	.picPreview {
		position: relative;
		width: 750rpx;
		height: 100vh;
		z-index: 99999;
		background-color: #acd998;

		movable-view {
			width: 750rpx;
			height: 530rpx;
		}

		movable-area {
			height: 100vh;
			width: 100%;
			position: fixed;
			overflow: hidden;
		}

		movable-view image {
			position: relative;
			width: 1000%;

			transform: translate3d(0, 0, 0) scale(0.1, 0.1);

			transform-origin: left top;
		}

		.top {
			position: fixed;
			top: 30rpx;
			right: 24rpx;
			width: 110rpx;
			height: 110rpx;
		}

		.bottom {
			position: fixed;
			left: 37rpx;
			bottom: 45rpx;
			width: 350rpx;
			height: 212rpx;
		}

		.popupBack {
			position: relative;
			margin: 50rpx auto;
			padding-top: 40px;
			width: 650rpx;
			height: 1016rpx;
			background-image: url(http://cdn.lianxia.top/static/shop/商家弹窗底.png);
			background-repeat: no-repeat;
			background-size: contain;
		}

		.pHeader {
			display: flex;
			justify-content: space-between;
			padding: 0 26rpx;
			margin-left: auto;
			margin-right: auto;
			margin-bottom: 50rpx;
			line-height: 108rpx;
			background-color: #fff;
			width: 470rpx;
			height: 108rpx;
			border-radius: 54rpx;

		}

		.headText {
			font-size: 50rpx;
			color: #fff;
			-webkit-text-stroke: 2rpx #ff9c4c;
			font-family: diy-font;
			font-weight: 1100;
		}

		.footerLocation {
			display: flex;
			justify-content: space-between;
			align-items: center;
			margin: 30rpx auto;
			padding: 0 25rpx;
			width: 511rpx;
			background-color: #fff;
			border-radius: 25rpx;
		}
	}
</style>