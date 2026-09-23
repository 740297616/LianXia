<template>
	<swiper class="swiper" indicator-color="rgba(255,255,255,0.5)" indicator-active-color="rgba(255,255,255,1)"
		:indicator-dots="true" :autoplay="true" :interval="3000" :duration="500" circular="true">

		<swiper-item v-for="(item,index) in swiperArr" :key="index" @click="swiperItemClick(item)">
			<view class="swiper-item">
				<image :src="item.image" :data-index="index" mode="aspectFill">
				</image>
			</view>
		</swiper-item>

	</swiper>
</template>

<script>
	export default {
		props: ['swiperArr'],

		methods: {
			swiperItemClick(item) {

				this.$emit('swiperItemClick', item);

			},
			/* 预览照片 */
			previewPhoto(e) {
				let index = e.currentTarget.dataset.index;
				let list = this.swiperArr.map((item, index) => {
					return item.image;
				});

				uni.previewImage({
					current: list[index],
					urls: list,
					longPressActions: {
						itemList: ['保存图片'],
						success: function(res) {

							uni.getImageInfo({
								src: list[res.index],
								success: function(image) {
									console.log('图片信息：', JSON.stringify(image));
									uni.saveImageToPhotosAlbum({
										filePath: image.path,
										success: function() {
											uni.showToast({
												title: '图片保存成功',
												icon: 'none',
												duration: 3000
											});
										}
									});
								}
							});
						}
					}
				});
			},

		}
	}
</script>

<style>
	.swiper {
		height: 340rpx;
	}

	.swiper-item image {
		margin: 0 auto;
		width: 504rpx;
		height: 337rpx;
		border-radius: 10rpx;
	}
</style>