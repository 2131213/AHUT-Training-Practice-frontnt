<template>
	<view class="u-p-t-40 u-p-r-60 u-p-b-30 u-p-l-60 login">
		<u-avatar size="140" src="/static/user.jpg" mode="circle"></u-avatar>
		<u-form class="forms" :model="loginModel" ref="form1">
			<u-form-item left-icon="account-fill" left-icon-style="font-size:24px;color:#4ec3e6;">
				<u-input placeholder="请输入账户" v-model="loginModel.username" />
			</u-form-item>
			<u-form-item left-icon="lock" left-icon-style="font-size:24px;color:#4ec3e6;">
				<u-input placeholder="请输入密码" v-model="loginModel.password" />
			</u-form-item>
			<view class="passtext">
				忘记密码
			</view>
			<u-button :custom-style="loginStyle">登录</u-button>
			<u-button type="success" :custom-style="registerStyle" @click="toRegister">注册</u-button>
		</u-form>
	</view>
</template>

<script setup>
	import {
		reactive
	} from 'vue';
	const loginModel = reactive({
		username: '',
		password: ''
	})
	//登录样式
	const loginStyle = reactive({
		marginTop: '40px',
		background: '#4ec3e6',
		color: '#FFF',
		width: '100%'
	})
	//注册按钮样式
	const registerStyle = reactive({
		marginTop: '35px',
		color: '#FFF',
		width: '100%'
	})
	
	//去注册
	const toRegister = () =>{
		uni.navigateTo({
			url:'../register/register'
		})
	}
</script>

<style lang="scss" scoped>
	.login {
		height: 100%;
		display: flex;
		align-items: center;
		flex-direction: column;

		.forms {
			width: 100%;
		}
	}

	.passtext {
		display: flex;
		justify-content: flex-end;
		color: #FF7670;
		margin-top: 15px;
	}
</style>