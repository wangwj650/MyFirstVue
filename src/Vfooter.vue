<template>
	<div id='footer'>
		<p>底部信息</p>
		<ul>
			<li v-for='item in citys'>{{item}}</li>
		</ul>
		<input type='text' v-model='city'/>
		<button @click='addcity'>添加</button>
	</div>
</template>
<script>
	export default {
		name:'VHeader',
		data() {
			return {
				city:''
			}
		},
		methods: {
			addcity:function() {
				//调用父组件自定义事件
				//在vue下面触发自定义事件
				//$emit(要触发的事件，要传递的参数)两个参数
				this.$emit('cityclick', this.city);
			}
		},
		props: {
			citys: Array
		}
	}
</script>
<style>
	#footer {
		width:100%;
		height: 50px;
		background-color: gray;
	}
</style>