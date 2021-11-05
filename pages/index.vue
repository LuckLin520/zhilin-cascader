<template>
	<view class="content">
		<zhilin-cascader v-model="show" :options="options" @confirm="onConfirm"></zhilin-cascader>
	</view>
</template>

<script>
	import ZhilinCascader from 'zhilin-cascader/zhilin-cascader'
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
		}
	]
	export default {
		components: {ZhilinCascader},
		data() {
			return {
				options,
				show: true
			}
		},
		methods: {
			onConfirm(value) {
				console.log(value)
			}
		},
		mounted() {
			// console.log(ZhilinCascader)
		}
	}
</script>

<style lang="scss">
</style>
