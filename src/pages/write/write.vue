<template>
	<view class="u-wrap u-p-l-40 u-p-r-40">
		<u-form :model="addModel" ref="form1">
			<u-form-item label="类型:">
				<view class="title">
					个人闲置物品
				</view>
			</u-form-item>
			<u-form-item label="名称:">
				<u-input placeholder="请输入名称" v-model="addModel.title" />
			</u-form-item>
			<u-form-item label="简介:">
				<u-input placeholder="请输入简介" v-model="addModel.introduce" />
			</u-form-item>
			<u-form-item label="价格:">
				<u-input placeholder="请输入价格" v-model="addModel.price" />
			</u-form-item>
			<u-form-item label-width="auto" label="联系人:">
				<u-input placeholder="请输入联系人" v-model="addModel.userName" />
			</u-form-item>
			<u-form-item label-width="auto" label="联系电话:">
				<u-input placeholder="请输入联系电话" v-model="addModel.phone" />
			</u-form-item>
			<u-form-item label="图片:"></u-form-item>
			<u-upload :action="action" :file-list="fileList"></u-upload>
		</u-form>
		<u-button :custom-style="customStyle">发布</u-button>
	</view>
</template>

<script setup>
	import {
		reactive,
		ref
	} from 'vue';
	//定义对象
	const addModel = reactive({
		type: '',
		title: '',
		introduce: '',
		price: '',
		userName: '',
		phone: '',
		image: ''
	})

	const value = ref('')
	const action = ref('')
	const fileList = ref([])

	const customStyle = reactive({
		background: '#00aaff',
		color: '#FFF',
		marginTop: '50px',
		width: '100%',
	})
</script>

<style lang="scss" scoped>
	.title {
		font-size: 20px;
		color: #10afcf;
		font-family: "黑体";
	}
</style>
