# cc-mySwiper


#### 使用方法

```使用方法
<!-- 自定义轮播图 swiperArr: 轮播数组  @swiperItemClick: 轮播图条目点击-->
<cc-mySwiper :swiperArr="banner" @swiperItemClick="swiperItemClick"></cc-mySwiper>

```

#### HTML代码实现部分
```html
<template>
	<view class="content">
		<!-- menuArr:导航菜单栏  @leftClick: 左导航按钮事件点击  @rigClick: 右导航按钮事件点击-->
		<cc-navHeader :menuArr="menuArr" @leftClick="leftClick" @rigClick="rigClick"></cc-navHeader>

		<!-- 自定义顶部搜索框 用于搜索跳转 skipUrl:跳转url为绝对路径 /pages开头 -->
		<cc-headSearch skipUrl="/pages/index/search"></cc-headSearch>

		<!-- 自定义轮播图 swiperArr: 轮播数组  @swiperItemClick: 轮播图条目点击-->
		<cc-mySwiper :swiperArr="banner" @swiperItemClick="swiperItemClick"></cc-mySwiper>

	</view>
</template>

<script>
	export default {


		data() {
			return {

				menuArr: [{
						"id": "1",
						"menu": "手机",
						"url": "/pages/phone/phone"
					},
					{
						"id": "2",
						"menu": "升学",
						"url": "/pages/study/study"
					},
					{
						"id": "3",
						"menu": "配件",
						"url": "/pages/parts/parts"
					},
					{
						"id": "4",
						"menu": "生活",
						"url": "/pages/life/life"
					}
				],
				banner: [{
						"id": 1,
						"image": "/static/image/banner1.jpg"
					},
					{
						"id": 2,
						"image": "/static/image/banner2.jpg"
					},
					{
						"id": 3,
						"image": "/static/image/banner3.jpg"
					},
					{
						"id": 4,
						"image": "/static/image/banner4.jpg"
					}
				]


			}
		},
		mounted() {

		},
		methods: {
			
			swiperItemClick(item){
				
				uni.showModal({
					title: '点击轮播图',
					content: '点击轮播图数据  = ' + JSON.stringify(item)
				})
			},
			leftClick(item) {

				uni.showModal({
					title: '点击导航栏按钮',
					content: '点击导航栏左侧搜索按钮 '
				})
			},
			rigClick(flag) {

				if (flag == 0) {
					uni.showModal({
						title: '点击导航栏按钮',
						content: '点击导航右侧购物车按钮 '
					})
				} else {

					uni.showModal({
						title: '点击导航栏按钮',
						content: '点击导航右侧更多按钮 '
					})
				}

			}


		}
	}
</script>

<style>
	page {

		background-color: #f7f7f7;
	}

	.content {
		display: flex;
		flex-direction: column;

	}
</style>

```
