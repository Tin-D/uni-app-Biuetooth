<template>
	<view class="">
		<view ref="qwe" id="myChart" :style="{width: '300px', height: '300px'}"></view>
	</view>
</template>

<script>
	// 引入基本模板
	let echarts = require('../../node_modules/echarts/lib/echarts')
	// 引入柱状图组件
	require('../../node_modules/echarts/lib/chart/bar')
	// 引入提示框和title组件
	require('../../node_modules/echarts/lib/component/tooltip')
	require('../../node_modules/echarts/lib/component/title')
	export default {
		name: 'hello',
		data() {
			return {
				msg: 'Welcome to Your Vue.js App'
			}
		},
		onReady() {
			console.log()
			this.$nextTick(function(){
				this.drawLine();
			})
		},
		methods: {
			drawLine() {
				// 基于准备好的dom，初始化echarts实例
				let myChart = echarts.init(this.$refs.qwe.$el)
				// 绘制图表
				myChart.setOption({
					title: {
						text: '在Vue中使用echarts'
					},
					tooltip: {},
					xAxis: {
						data: ["衬衫", "羊毛衫", "雪纺衫", "裤子", "高跟鞋", "袜子"]
					},
					yAxis: {},
					series: [{
						name: '销量',
						type: 'bar',
						data: [5, 20, 36, 10, 10, 20]
					}]
				});
			}
		}
	}
</script>

<style>

</style>
