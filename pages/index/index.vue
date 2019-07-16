<template>
	<view class="content">
		
		<view>
			<text class="title" @click="change">{{title}}</text>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				title: '登录成功'
			}
		},
		onLoad() {
			uni.request({
				url: 'https://www.easy-mock.com/mock/5d2d40d61499cb25afc95577/index', //仅为示例，并非真实接口地址。
				method: 'POST',
				data: {
					
				},
				
				success: (res) => {
					console.log(res.data);
				}
			});
		},
		methods: {
			change() {
				uni.navigateTo({
					url: '../details/details'
				});
			}
		}
	}
</script>

<style>
	.content {
		text-align: center;
		height: 400upx;
	}

	.logo {
		height: 200upx;
		width: 200upx;
		margin-top: 200upx;
	}

	.title {
		font-size: 36upx;
		color: #8f8f94;
	}
</style>
