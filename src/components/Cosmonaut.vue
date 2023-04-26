<script>
	export default {
		props: ['name','photo', 'mission', 'missionDate', 'missionLogo', 'side'],
		data() {
			return {
				showInfo: false,
				orientation: this.side
			}
		}
	}
</script>

<template>
	<div id="LeftContainer" @click="showInfo = true">
		<div id="Portrait" v-if="orientation == 'left'"></div>
		<div id="DetailGroup">
			<Transition>
				<div v-if="showInfo">
					<h1><span class="detail">Име</span> {{ name }}</h1>
					<h1><span class="detail">Мисия</span> {{ mission }}</h1>
					<h1><span class="detail">Дата на първо излитане</span> {{ missionDate}}</h1>
					<div id="Mission"></div>
				</div>
			</Transition>

			<h1 v-if="!showInfo" id="BigName">{{ name }}</h1>
		</div>
		<div id="Portrait" v-if="orientation == 'right'"></div>
	</div>
</template>

<style scoped>
	#Portrait {
		height: 98vh;
		border-radius: 20px;
		background-image: v-bind(photo);
		flex: 1;
		background-position: center;
		background-size: cover;
		background-repeat: no-repeat;
	}

	#Mission {
		width: 16vw;
		height: 45vh;
		background-repeat: no-repeat;
		background-size: contain;
 		background-image: v-bind(missionLogo);
	}
	
	* {color: white;}

	#BigName {
		position: absolute;
		padding-top: 20vh;
		padding-left: 30vh;
		font-size: 14vh;
	}
	.detail {
		padding-left: 20px;
		padding-right: 20px;
		padding-top: 10px;
		padding-bottom: 10px;
		border-radius: 10px;
		background-color: white;
		color: black;
		font-weight: 700;
	}

	img {border-radius: 20px;}

	#LeftContainer {
		display: flex;
		gap: 1vh;
		flex: 3;
		padding: .5vh 1vh;
	}

	#LeftContainer:hover {
		cursor:pointer;
	}

	#DetailGroup {
		background-color: rgb(149, 0, 0);
		border-radius: 20px;
		width: 100%;
		padding: 2vh;
		font-size: 3vh;
		flex: 2;
	}

	.v-enter-active, .v-leave-active {transition: opacity 0.5s ease;}

	.v-enter-from, .v-leave-to {opacity: 0;}
</style>