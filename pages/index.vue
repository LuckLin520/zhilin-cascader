<template>
	<view class="content">
		<button type="priamry" @click="show = !show">trigger</button>
		<zhilin-cascader v-model="show" :options="options" @confirm="onConfirm" :defaultSelected="defaultSelected"></zhilin-cascader>
	</view>
</template>

<script>
	// npm
	// import ZhilinCascader from 'zhilin-cascader/zhilin-cascader'
	const options = [{
			value: 'zhejiang',
			label: 'Zhejiang',
			children: [{
				value: 'hangzhou',
				label: 'Hangzhou',
				children: [{
					value: 'xihu',
					label: 'West Lake',
				}]
			}]
		},
		{
			value: 'jiangsu',
			label: 'Jiangsu',
			children: [{
				value: 'nanjing',
				label: 'Nanjing',
				children: [{
					value: 'zhonghuamen',
					label: 'Zhong Hua Men',
				}]
			}]
		},
		{
			value: 'hahahha',
			label: 'hahahah'
		}
	]
	export default {
		// npm
		// components: {ZhilinCascader},
		data() {
			return {
				options,
				show: false,
				defaultSelected: ['jiangsu', 'nanjing', 'zhonghuamen']
			}
		},
		methods: {
			onConfirm(value) {
				console.log(value)
			}
		}
	}
</script>

<style lang="scss">
	.content{
		padding-top: 10vh;
		button{
			width: 30%;
		}
	}
	
</style>
