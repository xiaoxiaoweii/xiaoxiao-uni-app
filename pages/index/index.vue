<template>
	<view class="content">
		<image class="logo" src="/static/logo.png"></image>
		<view class="text-area">
			<text class="title">{{title}}</text>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				title: 'Hello'
			}
		},
		onLoad() {
			this.getData()
		},
		methods: {
		// 获取轮播图的数据
			getData() {
				console.log('获取轮播图数据')
				uni.request({
					url: '/api/recipe/search?keyword=白菜&num=10&appkey=97c29c58f5b8932b',
					method: 'POST',
					success: (res) => {
						console.log(res)
						// if (res.data.status !== 0) {
						// 	return uni.showToast({
						// 		title: '获取数据失败',
						// 		icon: 'none'
						// 	})
						// }
						// this.swipers = res.data.message
					}
				})
			},
		}
	}
</script>

<style>
	.content {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
	}

	.logo {
		height: 200rpx;
		width: 200rpx;
		margin-top: 200rpx;
		margin-left: auto;
		margin-right: auto;
		margin-bottom: 50rpx;
	}

	.text-area {
		display: flex;
		justify-content: center;
	}

	.title {
		font-size: 36rpx;
		color: #8f8f94;
	}
</style>
