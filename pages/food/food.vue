<template>
	<view class="container" @touchmove.stop.prevent="disabledScroll">
		<view class="header">
			<view class="title"></view>
		</view>

		<scroll-view scroll-y="true" style="height: 83vh;">
			<view class="list">
				<view class="item" v-for="(item, index) in snacks" :key="index">
					<view @tap="open(item.id)">
						<image :src="item.img" alt="" mode="heightFix"
							style="display: block; margin: 12rpx auto; height: 178rpx;" />
						<view class="text">
							{{ item.name }}
						</view>
					</view>
				</view>
			</view>
		</scroll-view>

		<view>
			<uni-popup ref="popup" type="center" :animation="false">
				<view class="popupBack">
					<image src="http://cdn.lianxia.top/static/food/弹窗关闭图标.png" @tap="close"
						style="position: absolute; top:-16rpx; right:24rpx; width: 56rpx; height: 56rpx;"></image>
					<scroll-view scroll-y="true" style="width: 652rpx; height: 835rpx;">
						<view class="pHeader">
							<view
								style="margin-top: 45rpx; background-color: #ffea98; width: 16rpx; height: 16rpx; border-radius: 8rpx;">
							</view>
							<view class="headText" ref="myElement">{{ foodName }}</view>
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
							style="margin: 0 auto; margin-top: 35rpx; width: 510rpx; font-size: 30rpx; font-weight: 500; line-height: 47rpx;"
							v-html="foodText"></view>
						<view
							style="margin: 0 auto; margin-bottom: 50rpx; width: 510rpx; font-size: 30rpx; font-weight: 500; line-height: 47rpx;"
							v-html="foodShop"></view>
					</scroll-view>
				</view>
			</uni-popup>
		</view>
	</view>
</template>

<script>
	import foodJson from '../../static/json/food.json'
	export default {
		data() {
			return {
				foodSrc: '',
				foodName: '',
				foodText: "",
				foodShop: "",
				imgList: [],
				snacks: foodJson
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
			open(id) {
				this.foodSrc = this.snacks[id].img
				this.foodName = this.snacks[id].name
				this.foodText = this.snacks[id].text
				this.foodShop = this.snacks[id].shop
				this.imgList = this.snacks[id].imglist
				// 通过组件定义的ref调用uni-popup方法 ,如果传入参数 ，type 属性将失效 ，仅支持 ['top','left','bottom','right','center']
				this.$refs.popup.open('center')
			},
			disabledScroll() {
				if (this.change_pop_show) {
					return
				}
			},
			close() {
				this.$refs.popup.close()
			}
		}
	}
</script>

<style scoped>
	.container {
		min-height: 100vh;
		background-color: #b17b35;
	}

	.header {
		height: 200rpx;
		padding-top: 25rpx;
		text-align: center;
		background-color: #c69555;
	}

	.title {
		margin: 0 auto;
		width: 680rpx;
		height: 180rpx;
		background-image: url(../../static/food/小吃页面标题.png);
		background-repeat: no-repeat;
		background-size: contain;
	}

	.list {
		display: flex;
		justify-content: space-between;
		flex-wrap: wrap;
	}

	.item {
		position: relative;
		margin-top: 30rpx;
		width: 360rpx;
		height: 200rpx;
		background-color: #c69555;
	}

	.item .text {
		position: absolute;
		right: 0%;
		bottom: 0%;
		height: 50rpx;
		margin: 0 auto;
		overflow: contain;
		background-color: #fff;
		text-align: center;
		line-height: 50rpx;
		color: #8b3b1f;
		font-size: 34rpx;
		font-weight: 800;
		text-indent: 8rpx;
		letter-spacing: 5rpx;
		border-radius: 15rpx 0 0 0;
	}

	.popupBack {
		position: relative;
		margin: 180rpx auto;
		padding-top: 40px;
		width: 652rpx;
		height: 955rpx;
		/* overflow: hidden; */
		background-image: url(http://cdn.lianxia.top/static/food/小吃弹窗底图_compressed.png);
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
		font-size: 60rpx;
		color: #fff;
		-webkit-text-stroke: 3rpx #ff9c4c;
		font-family: diy-font;
		font-weight: 1100;
	}
</style>