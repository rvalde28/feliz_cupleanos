<template>
  <Carousel>
    <Slide v-for="(slide,i) in items" :key="slide">
        <!-- <div class="carousel__item">{{ slide }}</div> -->
        <!-- <img v-if="i==0" src="./assets/pics/uploads/IMG_3081.jpeg" > -->
        <div class="mobileView">
          <video class="videoClass mobile" v-if="i==0" controls Autoplay=autoplay>
            <source v-if="i==0" src="./assets/pics/uploads/4a0f7b507f3a46cf8f2d0221b5baf0d7.mov" type="video/mp4">
          </video>
          <div v-if="i==0" class="messageBox">
            <div v-if="i==0" class="messageBoard">Mi Frida bella, te deseo un muy feliz y bonito cumpleaños. Eres una persona tan especial que se merece el mundo. Que diosito te regale muchísimos años mas a lado de todos los que te queremos y que te la pases bonito mami, te amooo♥️</div>
            <div v-if="i==0" class="">- Karyme</div>
          </div>
        </div>

        <div class="mobileView">
          <div v-if="i==1" class="messageBox">
            <div v-if="i==1" class="messageBoard">Happy 22 dear friend! Enjoy your day! 🥳🎉🎊</div>
            <div v-if="i==1" class="">- Jandre</div>
          </div>
        </div>

        <div class="mobileView">
        <img v-if="i==2" src="./assets/pics/uploads/IMG_5836.jpeg" >
          <div v-if="i==2" class="messageBox">
            <div v-if="i==2" class="messageBoard">Feliz cumpleaños frida te quiero mucho te dare tu mejor regalo mi hijo traka de mujer dios te bendiga y que dios nos de muchos años mas de amistad ♥️trakaaa kheee de mujer🫶🏻✨</div>
            <div v-if="i==2" class="">- Dulce💜</div>
          </div>
        </div>

        <div class="mobileView">
          <img v-if="i==3" src="./assets/pics/uploads/IMG_5397.png" >
          <div v-if="i==3" class="messageBox">
            <div v-if="i==3" class="messageBoard">Happy Birthday Hermosa!!! 💐 🥳</div>
            <div v-if="i==3" class="">- Alejandra</div>
          </div>
        </div>

        <div class="mobileView">
          <div v-if="i==4" class="messageBox">
            <div v-if="i==4" class="messageBoard">Happy Birthday Frida!</div>
            <div v-if="i==4" class="">- Peter</div>
          </div>
        </div>

        <div class="mobileView">
          <div v-if="i==5" class="messageBox">
            <div v-if="i==5" class="messageBoard">Happy birthday Frida! Wishing many more 🎉</div>
            <div v-if="i==5" class="">- Danny Galvan</div>
          </div>
        </div>

        <div class="mobileView">
          <div v-if="i==6" class="messageBox">
            <div v-if="i==6" class="messageBoard">Happy birthday corazón de bonbon!!!💗🎉 I wish you the very best day and that it’s a blessed one. That God grants all your prayers and may your hope and dreams come true 🥹💗 so happy that I met such a beautiful soul like yours and that you’re in my life now. Sígale siendo un rayita del sol en nuestras vidas.TE QUIERO MUCHO PERRAAAAA MALDITA💗🍾🧁</div>
            <div v-if="i==6" class="">- Nina</div>
          </div>
        </div>

        <div class="mobileView">
          <img v-if="i==7" src="./assets/pics/uploads/IMG_2472.jpeg" >
          <div v-if="i==7" class="messageBox">
            <div v-if="i==7" class="messageBoard">Happy birthday frida!! I love you hoe 🩷"</div>
            <div v-if="i==7" class="">- Victoria</div>
          </div>
        </div>

        <div class="mobileView">
          <div v-if="i==8" class="messageBox">
            <div v-if="i==8" class="messageBoard">Muchas felicidades perre🥳🥳" un año mas y soporta"</div>
            <div v-if="i==8" class="">- Roxana❣️❣️</div>
          </div>
        </div>

        <div class="mobileView">
          <img v-if="i==9" src="./assets/pics/uploads/IMG_1328.jpeg" >
          <div v-if="i==9" class="messageBox">
            <div v-if="i==9" class="messageBoard">Mi Fridita hermosa feliz cumpleaños mi estrellita! 💫❤️ le doy muchas gracias a dios que nos a bendecido con tu presciencia, con tu sonrisa, con tus chistesitos, y con tu risa otro año más! No podría estar más emocionado por ti y por todo lo que has echo y por lo que vas a hacer. Nunca te voy a parar de querer mucho Fridita, nunca! Que dios te bendiga y te cuide siempre hermosa! ❤️ espero que tengas un cumpleaños muy bonito niña adulta de 22! 🎉"</div>
            <div v-if="i==9" class="">- Rubencito</div>
          </div>
        </div>

    </Slide>

    <template #addons>
      <Navigation />
      <Pagination />
    </template>
  </Carousel>
</template>

<script>
import { defineComponent } from 'vue'
import { Carousel, Navigation, Pagination, Slide } from 'vue3-carousel'

import 'vue3-carousel/dist/carousel.css'

export default defineComponent({
  name: 'Basic',
  components: {
    Carousel,
    Slide,
    Pagination,
    Navigation,
  },
  data() {
    return {
      items: [{},{},{},{},{},{},{},{},{},{}],
    }
  },
})
</script>

<style>
img{
  width: 400px!important;
  height: auto;
}

 @media only screen and (max-width: 2400px) and (min-width: 1400px)  {
  .videoClass{
    width: 400px!important; 
  }
  img{
    width: 250px !important;
    height: auto !important;
  }
}

@media only screen and (max-width: 1399px) and (min-width: 0px)  {
  .videoClass{
    width: 50vw!important;
    margin-bottom: 20vw;
  }
  img{
    width: 50vw!important;
    height: auto !important;
  }
  .mobileView{
    display: grid;
    grid-template: 1fr / 1fr;
    place-items: center;
  }

  .messageBox{
    width: 60vw!important;
    color: #2c3e50!important
  }

  .messageBoard{
    width: 60vw!important;
    height:auto;
  }
  .carousel__slide {
    padding: 4px!important;
  }
} 


.messageBox{
  display:inline-block;
}

.carousel__item {
  min-height: 200px;
  width: 100%;
  background-color: var(--vc-clr-primary);
  color: var(--vc-clr-white);
  font-size: 20px;
  border-radius: 8px;
  display: flex;
  justify-content: center;
  align-items: center;
}

.carousel__slide {
  padding: 10px;
}

.carousel__prev,
.carousel__next {
  box-sizing: content-box;
  border: 5px solid white;
}

.messageBoard{
  width: 500px;
  height:auto;
}

</style>
