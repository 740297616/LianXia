<template>
	<view>
		<view class="content">
			<!-- <image src="http://cdn.lianxia.top/static/index/视频底图.png" mode="" style="position: fixed; width: 750rpx; height: 100vh;"></image> -->
			<view class="col" v-for="(item,index) in list" :key="index" @click="play(item.videoId,index)">
				<video v-if="currentId == item.videoId" style="width: 690rpx;height: 390rpx; display: block;"
					autoplay="true" :id="'video'+item.videoId" :src="item.video" custom-cache=”true“></video>
				<block v-else>
					<image :src="item.img" style="height:390rpx;width:690rpx;display: block;"></image>
					<view class=" block">
						<view class="sanjia"></view>
					</view>
				</block>
				<view class="footer">
					<view class="name">
						{{item.name}}
					</view>
					<view class="right">
					</view>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	import videoJson from '../../static/json/video.json'
	export default {
		data() {
			return {
				list: [],
				currentId: 0,
				scrollH: 0,
				scrollTop: 0,
				height: 0,
				windowHeight: 0
			}
		},
		onLoad() {
			let that = this
			this.getList()
			// 获取可视区域高度
			uni.getSystemInfo({
				success: function(res) {
					that.windowHeight = res.windowHeight
				}
			})
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
		onPageScroll(res) {
			// 获取滚动距离
			this.scrollH = res.scrollTop
			// 判断元素是否已经出了可视区
			if (this.scrollH > this.scrollTop || this.scrollH + this.windowHeight < this.scrollTop) {
				const e = uni.createVideoContext("video" + this.currentId, this);
				e.pause()
			}
		},
		onHide() {
			this.currentId = 0
		},
		methods: {
			play(id, i) {
				this.currentId = id
				// 获取当前播放视频 元素距离顶部的高度
				if (this.height == 0) {
					uni.createSelectorQuery().select('.col').boundingClientRect((res) => {
						this.height = res.height
						this.scrollTop = res.height * (i + .5)
					}).exec()
				} else {
					this.scrollTop = this.height * (i + .5)
				}
			},
			getList() {
				this.list = videoJson
			}
		}
	}
</script>

<style lang="scss">
	page {
		background-color: #f2f2f2;
	}

	.content {
		padding: 30rpx;
	}

	.name {
		height: 80rpx;
		line-height: 80rpx;
		border-radius: 0 0 10px 10px;
		background-color: #FFFFFF;
		text-align: center;
		font-size: 14px;
	}

	.col {
		overflow: hidden;
		position: relative;
		overflow: hidden;
		margin-bottom: 30rpx;

		.block {
			position: absolute;
			width: 100%;
			height: 390rpx;
			background-color: rgba($color: #000000, $alpha: .3);
			left: 0;
			top: 0;
			display: flex;
			justify-content: center;
			align-items: center;

			.sanjia {
				width: 0;
				height: 0;
				border-top: 12px solid transparent;
				border-left: 17px solid #FFFFFF;
				border-bottom: 12px solid transparent;
			}
		}
	}
</style>