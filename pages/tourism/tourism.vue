<template>
	<view class="picPreview">
		<movable-area scale-area>
			<movable-view direction="all" @scale="onScale" scale="true" scale-min="2.65" scale-max="5"
				:scale-value="scaleValue" x="-500" y="-820" animation="false">
				<image :src="previewUrl" mode="widthFix">
					<view @tap="open(22)"
						style="position:absolute; top:360rpx; left:1500rpx; width:380rpx; height:250rpx;  background: url(http://cdn.lianxia.top/static/tourism/竹林书舍.png) top/contain no-repeat;font-size:0px;">
					</view>
					<view @tap="open(30)"
						style="position:absolute; top:20rpx; left:2030rpx; width:380rpx; height:290rpx;  background: url(http://cdn.lianxia.top/static/tourism/林氏宗祠.png) top/contain no-repeat;font-size:0px;">
					</view>
					<view @tap="open(29)"
						style="position:absolute; top:350rpx; left:2340rpx; width:380rpx; height:360rpx;  background: url(http://cdn.lianxia.top/static/tourism/郑氏宗祠.png) top/contain no-repeat;font-size:0px;">
					</view>
					<view @tap="open(23)"
						style="position:absolute; top:830rpx; left:1180rpx; width:520rpx; height:430rpx;  background: url(http://cdn.lianxia.top/static/tourism/树根门.png) top/contain no-repeat;font-size:0px;">
					</view>
					<view @tap="open(24)"
						style="position:absolute; top:670rpx; left:1960rpx; width:380rpx; height:350rpx;  background: url(http://cdn.lianxia.top/static/tourism/庸祖祠.png) top/contain no-repeat;font-size:0px;">
					</view>
					<view @tap="open(25)"
						style="position:absolute; top:740rpx; left:2480rpx; width:380rpx; height:400rpx;  background: url(http://cdn.lianxia.top/static/tourism/宋街.png) top/contain no-repeat;font-size:0px;">
					</view>
					<view @tap="open(16)"
						style="position:absolute; top:630rpx; left:3030rpx; width:380rpx; height:470rpx;  background: url(http://cdn.lianxia.top/static/tourism/丹砂古寺.png) top/contain no-repeat;font-size:0px;">
					</view>
					<view @tap="open(19)"
						style="position:absolute; top:1020rpx; left:1740rpx; width:380rpx; height:410rpx;  background: url(http://cdn.lianxia.top/static/tourism/蔡氏宗祠.png) top/contain no-repeat;font-size:0px;">
					</view>
					<view @tap="open(17)"
						style="position:absolute; top:1150rpx; left:2260rpx; width:380rpx; height:340rpx;  background: url(http://cdn.lianxia.top/static/tourism/杏园书屋.png) top/contain no-repeat;font-size:0px;">
					</view>
					<view @tap="open(21)"
						style="position:absolute; top:1110rpx; left:2820rpx; width:380rpx; height:390rpx;  background: url(http://cdn.lianxia.top/static/tourism/晏侯庙.png) top/contain no-repeat;font-size:0px;">
					</view>
					<view @tap="open(12)"
						style="position:absolute; top:40rpx; left:3520rpx; width:420rpx; height:380rpx;  background: url(http://cdn.lianxia.top/static/tourism/佬园山公园.png) top/contain no-repeat;font-size:0px;">
					</view>
					<view @tap="open(11)"
						style="position:absolute; top:100rpx; left:3960rpx; width:380rpx; height:460rpx;  background: url(http://cdn.lianxia.top/static/tourism/窖东公园.png) top/contain no-repeat;font-size:0px;">
					</view>
					<view @tap="open(26)"
						style="position:absolute; top:600rpx; left:3940rpx; width:680rpx; height:470rpx;  background: url(http://cdn.lianxia.top/static/tourism/虎丘山石刻.png) top/contain no-repeat;font-size:0px;">
					</view>
					<view @tap="open(27)"
						style="position:absolute; top:1040rpx; left:3640rpx; width:380rpx; height:330rpx;  background: url(http://cdn.lianxia.top/static/tourism/乃秋小庐.png) top/contain no-repeat;font-size:0px;">
					</view>
					<view @tap="open(20)"
						style="position:absolute; top:1200rpx; left:3320rpx; width:380rpx; height:460rpx;  background: url(http://cdn.lianxia.top/static/tourism/古榕道.png) top/contain no-repeat;font-size:0px;">
					</view>
					<view @tap="open(28)"
						style="position:absolute; top:1410rpx; left:1210rpx; width:380rpx; height:550rpx;  background: url(http://cdn.lianxia.top/static/tourism/鸡翁树.png) top/contain no-repeat;font-size:0px;">
					</view>
					<view @tap="open(18)"
						style="position:absolute; top:1440rpx; left:1670rpx; width:380rpx; height:450rpx;  background: url(http://cdn.lianxia.top/static/tourism/古葵庵.png) top/contain no-repeat;font-size:0px;">
					</view>
					<view @tap="open(6)"
						style="position:absolute; top:1530rpx; left:2890rpx; width:420rpx; height:420rpx;  background: url(http://cdn.lianxia.top/static/tourism/陶源谷农场.png) top/contain no-repeat;font-size:0px;">
					</view>
					<view @tap="open(7)"
						style="position:absolute; top:2180rpx; left:1910rpx; width:420rpx; height:450rpx;  background: url(http://cdn.lianxia.top/static/tourism/滨河洲公园.png) top/contain no-repeat;font-size:0px;">
					</view>
					<view @tap="open(3)"
						style="position:absolute; top:2000rpx; left:5550rpx; width:670rpx; height:470rpx;  background: url(http://cdn.lianxia.top/static/tourism/党建广场.png) top/contain no-repeat;font-size:0px;">
					</view>
					<view @tap="open(4)"
						style="position:absolute; top:2230rpx; left:4720rpx; width:380rpx; height:400rpx;  background: url(http://cdn.lianxia.top/static/tourism/许氏家庙.png) top/contain no-repeat;font-size:0px;">
					</view>
					<view @tap="open(10)"
						style="position:absolute; top:2510rpx; left:5160rpx; width:420rpx; height:380rpx;  background: url(http://cdn.lianxia.top/static/tourism/王鼎新故居.png) top/contain no-repeat;font-size:0px;">
					</view>
					<view @tap="open(14)"
						style="position:absolute; top:2710rpx; left:4300rpx; width:520rpx; height:480rpx;  background: url(http://cdn.lianxia.top/static/tourism/立德乐琴间馆.png) top/contain no-repeat;font-size:0px;">
					</view>
					<view @tap="open(1)"
						style="position:absolute; top:3060rpx; left:5030rpx; width:520rpx; height:290rpx;  background: url(http://cdn.lianxia.top/static/tourism/侨史室.png) top/contain no-repeat;font-size:0px;">
					</view>
					<view @tap="open(2)"
						style="position:absolute; top:3200rpx; left:4750rpx; width:380rpx; height:430rpx;  background: url(http://cdn.lianxia.top/static/tourism/建阳乐园.png) top/contain no-repeat;font-size:0px;">
					</view>
					<view @tap="open(13)"
						style="position:absolute; top:3730rpx; left:4680rpx; width:420rpx; height:530rpx;  background: url(http://cdn.lianxia.top/static/tourism/蔡寮荣禄第.png) top/contain no-repeat;font-size:0px;">
					</view>
					<view @tap="open(5)"
						style="position:absolute; top:3530rpx; left:5690rpx; width:380rpx; height:530rpx;  background: url(http://cdn.lianxia.top/static/tourism/馨乐园.png) top/contain no-repeat;font-size:0px;">
					</view>
					<view @tap="open(9)"
						style="position:absolute; top:3530rpx; left:6400rpx; width:520rpx; height:330rpx;  background: url(http://cdn.lianxia.top/static/tourism/北湾文明广场.png) top/contain no-repeat;font-size:0px;">
					</view>
					<view @tap="open(8)"
						style="position:absolute; top:3880rpx; left:6700rpx; width:520rpx; height:490rpx;  background: url(http://cdn.lianxia.top/static/tourism/北湾文化公园.png) top/contain no-repeat;font-size:0px;">
					</view>
					<view @tap="open(15)"
						style="position:absolute; top:4500rpx; left:4400rpx; width:380rpx; height:490rpx;  background: url(http://cdn.lianxia.top/static/tourism/莲阳公园.png) top/contain no-repeat;font-size:0px;">
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
							<view class="headText" ref="myElement">{{ tourismName }}</view>
							<view
								style="margin-top: 45rpx; background-color: #ffea98; width: 16rpx; height: 16rpx; border-radius: 8rpx;">
							</view>
						</view>
						<view style="position: relative; width: 504rpx; height: 337rpx;margin:0 auto ;">
							<cc-mySwiper :swiperArr="imgList"></cc-mySwiper>
							<image src="http://cdn.lianxia.top/static/tourism/地图弹窗【文旅】浮层贴纸.png" mode="heightFix"
								style="display: block; position: absolute; top:-23rpx; left: -33rpx; height: 90rpx; width: 133rpx;">
							</image>
							<image src="http://cdn.lianxia.top/static/tourism/地图弹窗【文旅】浮层贴纸2.png" mode="heightFix"
								style="display: block; position: absolute; bottom:-23rpx; right: -33rpx; height: 90rpx;">
							</image>
						</view>
						<view
							style="margin: 0 auto; margin-top: 40rpx; width: 510rpx; font-size: 30rpx; font-weight: 500;"
							v-html="tourismText"></view>
						<view class="footerLocation" @tap="openLoca">
							<view
								style="display: inline; margin: 20rpx 0; width: 410rpx; font-size: 30rpx; font-weight: 500; line-height:42rpx;"
								v-html="tourismLocation"></view>
							<image src="http://cdn.lianxia.top/static/tourism/地图弹窗【地址】导航图标.png"
								style="margin: 20rpx 0;; width: 70rpx; height: 70rpx;"></image>
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
	import tourismjson from '../../static/json/tourism.json'
	export default {
		data() {
			return {
				tourismSrc: '',
				tourismName: '',
				imgList: [],
				tourismText: "",
				tourismaArray: tourismjson,
				tourismLat: 1,
				tourismLng: 1,
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
				this.tourismName = this.tourismaArray[id - 1].Name
				this.imgList = this.tourismaArray[id - 1].imglist
				this.tourismText = this.tourismaArray[id - 1].Introduction
				this.tourismLocation = this.tourismaArray[id - 1].Address
				this.tourismLat = this.tourismaArray[id - 1].lat
				this.tourismLng = this.tourismaArray[id - 1].lng
				this.imgFrom = this.tourismaArray[id - 1].from
				this.$refs.popup.open('center')
			},
			close() {
				this.$refs.popup.close()
			},
			openLoca() {
				uni.openLocation({
					latitude: Number(this.tourismLng),
					longitude: Number(this.tourismLat),
					name: this.tourismName,
					address: this.tourismLocation,
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
			background-image: url(http://cdn.lianxia.top/static/地图弹窗【文旅】底图.png);
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
			margin-bottom: 50rpx;
			padding: 0 25rpx;
			width: 511rpx;
			background-color: #fff;
			border-radius: 25rpx;
		}
	}
</style>