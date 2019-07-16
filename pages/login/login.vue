<template>
	<view class="container">
		<view class="title">
			
			<image class="img-logo" mode="aspectFit" src="../../static/logo.png"></image>
		</view>
		<view class="login-box">
			<view class="username-wrap">
				<input type="text" class="username" v-model="userName" />
			</view>
			<view class="password-wrap">
				<input type="password" class="password" v-model="passWord" />
			</view>
			<view class="btn">
				<button @click="submitEvent">登录</button>
			</view>
		</view>
		<uni-popup ref="popup" type="center" class="popup">
			用户名或密码不能为空
			<button @click="closePopup" style="margin-top: 20upx;">关闭</button>
		</uni-popup>
	</view>
</template>

<script>
	import uniPopup from "@/components/uni-popup/uni-popup.vue"
	export default {
		data() {
			return {
				userName: '',
				passWord: ''
			};
		},
		methods: {
			submitEvent() {
				if(this.userName=='' || this.passWord=='') {
					this.$refs.popup.open();
					return 
				}
				console.log(this.userName)
				console.log(this.passWord)
				uni.redirectTo({
					url: '../index/index'
				});
			},
			closePopup(){
				this.$refs.popup.close();
			}
		},
		components: {uniPopup}
	}
</script>

<style lang="less">
.container {
	position: absolute;
	left: 0;
	right: 0;
	top: 0;
	bottom: 0;
	width: 100%;
	height: 100%;
}
.title {
	height: 500upx;
	width: 100%;
	background: linear-gradient(to right,#0175c6,#0598e4); /* Safari 5.1 - 6.0 */
	position: relative;
	.img-logo {
		width: 100px; 
		height: 100px; 
		background-color: #eeeeee;
		position: absolute;
		left: 50%;
		top: 50%;
		transform: translate(-50%,-50%);
	};
}
.login-box {
	width: 100%;
	margin-top: 50upx;
}
.username-wrap {
	padding: 0 120upx;
	display: flex;
	.username {
		height: 60upx;
		flex: 2;
		float: right;
		border-bottom: 1px solid #ccc;
		background: #fff;
	}
	
}
.password-wrap {
	margin-top: 60upx;
	display: flex;
	padding: 0 120upx;
	.password {
		height: 60upx;
		flex: 2;
		float: right;
		border-bottom: 1px solid #ccc;
		background: #fff;
	}
}
.btn {
	margin-top: 50upx;
	padding: 0 100upx;
	button {
		
		background: #0598e4;
		color: #fff;
	}
}
.popup {
	height: 100%;
}
</style>
