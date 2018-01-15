<template>
	<div id="marked">
		<textarea class="editor" name="" id="" cols="30" rows="10" v-model='text'></textarea>
		<div class="screen" v-html='newtext'></div>
	</div>
</template>
<script>
//npm install marked 需要安装Markdown解析器
import marked from 'marked'
	export default {
		name: 'Vmarked',
		data() {
			return {
				text:''
			}
		},
		computed: {
			newtext: function() {
				// 解析左侧输入内容
				return marked(this.text);
			}
		}
	}
</script>
<style>
	#marked {
		width :1000px;
		margin:30px auto;
		overflow: hidden;
	}
	.editor, .screen {
		float: left;
		width: 50%;
		border: 1px solid #ccc;
		box-sizing: border-box;
		height: 300px;
	}
	textarea{
		height: 100%;
		width:100%;
		border: none;
		background-color: transparent;
	}
</style>