<script lang="ts">
import Cosmonaut from './components/Cosmonaut.vue'
import Gallery from './components/Gallery.vue'
import Image from "./components/Image.vue"
import Notchev from "./components/Notchev.vue"
export default {
  data() {
    return {
      textColor: 'white',
      BGColor: 'black',
      altTextColor: 'black',
      altTextBGColor: 'white',
      BGImage: 'none'
    }
  },
  components: {Cosmonaut, Gallery, Image, Notchev},
  methods: {
    changeIntoDark() {
      this.textColor = 'white'
      this.BGColor = 'black'
      this.altTextColor = 'black'
      this.altTextBGColor = 'white'
      this.BGImage = 'none'
    },
    changeIntoWhite() {
      this.textColor = 'black'
      this.BGColor = 'white'
      this.altTextColor = 'white'
      this.altTextBGColor = 'black'
      this.BGImage = 'none'
    },
    addMoon() {
      this.BGImage = 'url("moon.jpg")'
    }
  }
}
</script>

<template>
  <div id="Bakur">
    <div>
      <h1 style="margin-bottom: -5vh; margin-top: -1vh">Българския принос в космонавтиката</h1>
      <p>Изготвено от Петър Владов</p>
    </div>

    <div>
      <h1 style="margin-bottom: -5vh">НАО <span>Рожен</span></h1>
      <p>Първи стъпки в развитието на българската космонавтика</p>
      <Gallery>
        <Image content="url('Rozhen.jpg')" title="Рожен"
        subtitle="Националната астрономическа обсерватория Рожен е 
        най-голямата астрономическа обсерватория 
        в Югоизточна Европа и на Балканския полуостров.
        Обсерваторията е открита на 13.03.1981.
        Намира се в Родопите, близо до Чепеларе."/>

        <Image content="url('Pravets-16H.png')" title="Правец-16Н"
        subtitle="16-битов компютър, използван в
        астрономическия комплекс Рожен с научни цели.
        Една задача, чиято отговорност е на компютъра е
        обработката на снимки на космически обекти в реално време."/>

        <Image content="url('Pleven-87.jpg')" title="Плевен-87"
        subtitle="Компютърна система за изследване на 
        висшите психични функции и емоционално-волевата устойчивост и 
        надеждност на космонавтите – космически психотест."/>
      </Gallery>
    </div>

    <div>
      <h1>Проектът 
      <span>Спектър-15</span></h1>
      <p id="subtitle1">Що е то?</p>

      <Gallery>
        <Image style="flex: 1" />
        <Image style="flex: 20" content="url('Camera.jpg')" title="Камерата на Спектър-15"
        subtitle="От нея се получава информация за излъчената от Слънцето
        и другите космически обекти светлина. Една цел за това е изучаването
        на свойствата и характеристиките на други космически обекти 
        (планети, звезди, т.н.)."/>
        <Image style="flex: 1" />
      </Gallery>

      <Gallery>
        <Image style="flex: 1" />
        <Image style="flex: 20" content="url('Casette-Recorder.jpg')" 
        title="Касетофонът на Спектър-15"
        subtitle="Чрез него, информацията, придобита от камерата, се записва на касети.
        Може да се каже, че касетите са вид 'харддиск'."/>
        <Image style="flex: 1" />
      </Gallery>

      <h1 style="padding: 10vh 0vh">Първите български космонавти</h1>

      <Cosmonaut name="Георги Иванов" mission="Союз-33" 
      missionDate="10 април 1979" side='right'
      missionLogo="url('missions/Soyuz-33.png')"
      photo="url('cosmonauts/Georgi-Ivanov.jpg')"></Cosmonaut>

      <Cosmonaut name="Александър Александров" mission="Союз-TM4, Союз-TM5" 
      missionDate="21 декември 1987" side='left'
      missionLogo="url('missions/Soyuz-TM5.png')"
      photo="url('cosmonauts/Aleksandar-Aleksandrov.jpg')"></Cosmonaut>
    </div>

    <div style="padding: 28vh 0vh; background-image: url('moon.jpg');"
    @wheel="changeIntoDark()"
    @mouseenter="changeIntoDark()">
      <h1>Аполо-11</h1>
      <p>кацва на Луната на <span>16 юли 1969</span></p>
    </div>
    <h1 style="margin-top: 360px">Но знаете ли, че...</h1>
    <p>инженера на двигателите е</p>
    <p><span>българин?</span></p>
    <br>
    <h1>Точно така!</h1>
    <p>Това е той:</p>
    
    <Notchev />

    <hr style="width: 100vw; border: 1vw white solid;">
    <h1 style="margin-top: 360px">Знаете ли, че...</h1>
    <p>има <span>български</span> изкуствен спътник?</p>
    <Gallery>
      <Image />
      <Image style="flex: 4" content="url('Satellite.jpeg')" 
        title="Спътникът 'България-1300'"
        subtitle="Изтрелва се в космоса в чест на 1300 години българска държава.
        Главната му цел е да изучава магнитосферата и йоносферата на Земята.
        Другото му име е 'Интеркосмос-22'."/>
      <Image />
    </Gallery>

    <Gallery>
      <Image />
      <iframe style="flex: 20" src="https://sky.rogue.space/?intldes=1981-075A" frameborder="0"></iframe>
      <Image />
    </Gallery>

    <p><span>https://sky.rogue.space/</span></p>

    <h1>Благодаря за вниманието!</h1>

<!--     <div v-for="n in 2077">
      <h1><i>Cyberpunk {{ n }}</i></h1>
    </div> -->
  </div>
  
</template>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Oswald:wght@200&display=swap');

#Bakur {
  margin: 0;
  display: flex;
  flex-direction: column;
  gap: 1.2vh;
  background-color: v-bind(BGColor);
  background-image: v-bind(BGImage);
  background-position: center;
  background-size: auto;
  overflow-x: hidden;
}

* {
  user-select: none;
  font-family: 'Oswald';
  transition: 1s cubic-bezier(0.175, 0.885, 0.32, 1.275) color;
  transition: 1s cubic-bezier(0.175, 0.885, 0.32, 1.275) background-color;
  color: v-bind(textColor);
}

span {
  padding: 5vh; border-radius: 20px;
  color: v-bind(altTextColor);
  background-color: v-bind(altTextBGColor);
}

h1 {
  font-size: 20vh;
  text-align: center;
}

p {
  font-size: 15vh;
  text-align: center;
}
</style>