<script>
export default {
	props: ['content', 'title', 'subtitle'],
	data() {
		return {
			showText: false,
		}
	}
}
</script>

<template>
	<div id="GalleryImage" @click="showText = !showText">
		<Transition>
			<div id="TextContainer" v-if="showText">
				<h1>{{ title }}</h1>
				<p>{{ subtitle }}</p>
			</div>
		</Transition>
	</div>
</template>

<style scoped>
	#GalleryImage {
		display: flex;
		justify-content: center;
		text-align: center;
		margin: 0;
		height: 98vh;
		background-image: v-bind(content);
		background-repeat: no-repeat;
		background-size: cover;
		background-position: center;
		border-radius: 20px;
		flex: 1;
		overflow: hidden;
	}

	#GalleryImage:hover {
		cursor: pointer;
	}

	#TextContainer {
		font-size: 5vh;
		width: 100%;
		color: white;
		background-color: rgba(40, 40, 40, .80);
	}

	.v-enter-active, .v-leave-active {
  	transition: opacity 0.5s ease;
	}

	.v-enter-from, .v-leave-to {
		opacity: 0;
	}

</style>

