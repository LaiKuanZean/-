<!-- 在 head 部分添加以下链接 -->
<script src="https://cdn.jsdelivr.net/npm/apexcharts"></script>
<template>
	<div id="chart"></div>
  </template>
  
  <script>
  import ApexCharts from 'apexcharts';
  import VueApexCharts from 'vue-apexcharts';
  
  export default {
	components: {
	  apexchart: VueApexCharts,
	},
	data() {
	  return {
		options: {
		  series: [
			{ data: [44, 55, 41, 64, 22, 43, 21] },
			{ data: [53, 32, 33, 52, 13, 44, 32] },
		  ],
		  chart: {
			type: 'bar',
			height: 430,
		  },
		  plotOptions: {
			bar: {
			  horizontal: true,
			  dataLabels: {
				position: 'top',
			  },
			},
		  },
		  dataLabels: {
			enabled: true,
			offsetX: -6,
			style: {
			  fontSize: '12px',
			  colors: ['#fff'],
			},
		  },
		  stroke: {
			show: true,
			width: 1,
			colors: ['#fff'],
		  },
		  tooltip: {
			shared: true,
			intersect: false,
		  },
		  xaxis: {
			categories: [2001, 2002, 2003, 2004, 2005, 2006, 2007],
		  },
		},
	  };
	},
	mounted() {
	  const chart = new ApexCharts(document.querySelector('#chart'), this.options);
	  chart.render();
	},
  };
  </script>
  <template>
	<div>
	  <my-chart />
	</div>
  </template>
  
  <script>
  import MyChart from '@/components/MyChart.vue';
  
  export default {
	components: {
	  MyChart,
	},
  };
  </script>
  