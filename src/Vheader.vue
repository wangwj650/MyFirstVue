<template>
	<header id='top'>
		<img :src='logosrc' alt='这是logo'/>
	</header>
</template>
<script>
	import logosrc from './assets/logo.png'
	export default {
		name:'VHeader',
		data() {
			return {
				logosrc: logosrc
			}
		}
	}
</script>
<style scoped>
	#top {
		width: 100%;
		height: 50px;
		background-color: gray;
	}
	img {
		width:50px;
		height:50px;
	}
</style>