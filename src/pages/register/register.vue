<template>
	<view class="u-p-t-40 u-p-r-60 u-p-b-30 u-p-l-60 register">
		<button class="avatarwrap" open-type="chooseAvatar" bind:chooseavatar="onChooseAvatar">
			<image class="avatar" :src="avatarUrl"></image>
		</button>
		<!-- <u-avatar size="140" src="/static/user.jpg" mode="circle"></u-avatar> -->
		<u-form class="forms" :model="loginModel" ref="form1">
			<u-form-item left-icon="phone" left-icon-style="font-size:24px;color:#4ec3e6;">
				<u-input placeholder="请输入电话" v-model="loginModel.phone" />
			</u-form-item>
			<u-form-item left-icon="account" left-icon-style="font-size:24px;color:#4ec3e6;">
				<u-input placeholder="请输入账户" v-model="loginModel.username" />
			</u-form-item>
			<u-form-item left-icon="lock" left-icon-style="font-size:24px;color:#4ec3e6;">
				<u-input placeholder="请输入密码" v-model="loginModel.password" />
			</u-form-item>
			<u-form-item left-icon="lock" left-icon-style="font-size:24px;color:#4ec3e6;">
				<u-input placeholder="请输入确定密码" v-model="loginModel.password" />
			</u-form-item>
			<view class="passtext" @click="toLogin">
				已有账号，去登录
			</view>
			<u-button :custom-style="registerStyle">注册</u-button>
		</u-form>
	</view>
</template>

<script setup>
	import {
		reactive,
		ref
	} from 'vue';
	const loginModel = reactive({
		phone: '',
		username: '',
		password: ''
	})
	const registerStyle = reactive({
		marginTop: '40px',
		background: '#4ec3e6',
		color: '#FFF',
		width: '100%'
	})
	const customStyle2 = reactive({
		marginTop: '35px',
		// background:'#FF7670',
		color: '#FFF',
		width: '100%'
	})
	const onChooseAvatar = (e) => {

	}
	const avatarUrl = ref('/static/user.jpg')
	
	const toLogin = () =>{
		uni.navigateTo({
			url:'../login/login'
		})
	}
</script>

<style lang="scss" scoped>
	.register {
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

	.avatarwrap {
		border-radius: 100%;
		display: flex;
		justify-content: center;
		align-items: center;
		height: 70px;
		width: 70px;
		padding: 0px;

		.avatar {
			border-radius: 100%;
			height: 70px;
			width: 70px;
		}
	}
</style>
