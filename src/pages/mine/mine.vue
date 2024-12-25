<template>
	<view class="page">
		<view class="u-flex user-box u-p-30">
			<view class="u-m-r-10">
				<u-avatar src="/static/user.jpg" size="100"></u-avatar>
			</view>
			<view class="u-flex-1">
				<view class="u-font-18 u-p-b-20">安徽工业大学</view>
			</view>
			<view class="u-m-l-10 u-p-10">
				<u-icon name="arrow-right" color="#969799" size="28"></u-icon>
			</view>
		</view>
		<view class="u-m-t-20">
			<u-cell-group>
				<u-cell-item icon="man-add" title="我的发布"></u-cell-item>
				<u-cell-item icon="heart" title="我的收藏"></u-cell-item>
				<u-cell-item icon="red-packet" title="购买记录"></u-cell-item>
				<u-cell-item icon="order" title="出售记录"></u-cell-item>
				<u-cell-item icon="edit-pen" title="修改密码"></u-cell-item>
				<u-cell-item icon="setting" title="退出账号" @click="loginOut"></u-cell-item>
			</u-cell-group>
		</view>
		<view class="u-m-t-20">
			<u-cell-group>
					<u-cell-item icon="setting-fill" title="个人设置"></u-cell-item>
					<u-cell-item icon="integral-fill" title="会员等级" value="新版本"></u-cell-item>
				</u-cell-group>
		</view>
	</view>
</template>

<script setup>


const loginOut = () =>{
	uni.navigateTo({
		url: '../login/login'
	})
}

</script>

<style lang="scss" scoped>
   .page {
		background-color: #ededed;
	}
	.user-box {
		background-color: #fff;
	}
</style>
