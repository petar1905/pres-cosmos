<script>
	export default {
		props: ['name','photo', 'mission', 'missionDate', 'missionLogo', 'side'],
		data() {
			return {
				showInfo: false,
				orientation: 'left'
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
					<h1><span class="detail">Име</span> д-р инж. Иван Ночев</h1>
					<h1><span class="detail">Основно образование</span> Механо-техническото училище в Карлово</h1>
					<h1><span class="detail">Висше образование</span> Берлинска Политехника</h1>
					<h1><span class="detail">Работи върху</span> двигателите на Аполо-11</h1>
					<div id="Mission"></div>
				</div>
			</Transition>

			<h1 v-if="!showInfo" id="BigName">Иван Ночев</h1>
		</div>
		<div id="Portrait" v-if="orientation == 'right'"></div>
	</div>
</template>

<style scoped>
	#Portrait {
		height: 98vh;
		border-radius: 20px;
		background-image: url('Ivan-Notchev.png');
		flex: 1;
		background-position: center;
		background-size: cover;
		background-repeat: no-repeat;
	}

	#Mission {
		width: 14vw;
		height: 27vh;
		background-repeat: no-repeat;
		background-size: contain;
 		background-image: url('missions/Apollo-11.png');
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
		background-color: rgb(0, 40, 149);
		border-radius: 20px;
		width: 100%;
		padding: 2vh;
		font-size: 3vh;
		flex: 2;
	}

	.v-enter-active, .v-leave-active {transition: opacity 0.5s ease;}

	.v-enter-from, .v-leave-to {opacity: 0;}
</style>