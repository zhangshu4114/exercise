<template>
	<div v-bind:style="{height:application.height}">
		<el-container>
			<!-- 导航栏 -->
			<el-header>
				<nav_header></nav_header>
			</el-header>
			<!--主体部分-->
			<el-main style='height: 900px;'>
				<main_content></main_content>
			</el-main>
			<!--版权部分-->
			<el-footer></el-footer>
		</el-container>
	</div>
</template>
<script>
	import nav_header from '/src/views/header/nav_header';
	import main_content from '/src/views/main/main-content';
	export default {
		name:'application',
		data:function(){
			const data = {
				application:{
					height:''
				}
			}
			return data;
		},
		components:{
			nav_header,
			main_content
		},
		mounted:function(){
			const height = document.documentElement.clientHeight;
			this.application.height = height + 'px';
		}
	}
</script>
<style>
	.el-header,
	.el-footer {
		background-color: #FDDCE1;
		color: #333;
		text-align: center;

	}

	.el-aside {
		background-color: #D3DCE6;
		color: #333;
		text-align: center;

	}

	.el-main {
		background-color: #E9EEF3;
		color: #333;
		text-align: center;

	}

	body>.el-container {
		margin-bottom: 40px;
	}


	[size='10']{
		min-height: 10px;
	}

</style>
