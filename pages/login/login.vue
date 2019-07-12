<template>
	<view>
		<view class="username-wrap">
			用户名：<input type="text" class="username" v-model="userName" />
		</view>
		<view class="password-wrap">
			密码：<input type="password" class="password" v-model="passWord" />
		</view>
		<view class="btn">
			<button @click="submitEvent">登录</button>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				userName: '',
				passWord: ''
			};
		},
		methods: {
			submitEvent() {
				console.log(this.userName)
				console.log(this.passWord)
			}
		},
	}
</script>

<style lang="less">
.username-wrap {
	.username {
		float: right;
		border: 1px solid #eee;
	}
	
}
.password-wrap {
	.password {
		float: right;
		border: 1px solid #eee;
	}
}
</style>
