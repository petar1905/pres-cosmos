<script>
export default {components: {Image}}
</script>

<template>
	<div id="Gallery">
		<slot></slot>
	</div>
</template>

<style scoped>
	#Gallery {
		display: flex;
		gap: 1vh;
		padding: 1vh;
	}
</style>