<script>
import MessageComponent from './components/MessageComponent.vue'
import moment from 'vue-moment';
// let msg = "ya mero cumples anos Fridita! ya es dia de tu cumpleanos?"
// cp -r /mnt/c/Users/Ruben/OneDrive/Pictures/frida_website/ fridas_birthday/src/assets/gifs/
export default {
  name: "App",
  data() {
    return {
      msg: "¡Ya mero cumples años Fridita! \n Ya es dia de tu cumpleaños?",
      msg2: "",
      isHidden: false,
      showSecond: false,
      firstGifShow: true,
      secondGifShow: false,
      thirdGifShow: false
    };
  },
  methods: {
    changeMessageMentirosa(){
      this.msg = 'A que no hermosa todavia no.... 🥲💔'
      this.isHidden = true
      this.showSecond = true
    },
    changeMessageWithDaysLeft(){
      this.isHidden = true
      this.firstGifShow=false
      this.thirdGifShow= true
      var eventStartTime = +new Date()- +new Date("2024-03-22T00:00:00.000Z")
      const timeDifferenceInHours = eventStartTime / (1000 * 60 * 60);

      const hours = Math.ceil(timeDifferenceInHours * -1)
      const days = Math.ceil(hours/24)+1
      console.log(days)
      this.msg = `¡¡Ya mero llega tu dia especial, solo faltan ${days} dias!! Por lo tanto tienes que esperar mi niña hermosa...`
    },
    changeMessageSecondGif(){
      this.msg = 'Te dejo con un show privado y exclusivo😉'
      this.msg2 = 'PS: Ay te encargo que le dejes un buen tip porfa'
      this.firstGifShow = false
      this.secondGifShow= true
      this.showSecond=false
    },
  },
  components: {
    MessageComponent,
  },
  // rest of the component
};
</script>

<template>
  <div class="balloon-box"> 
    <div class="balloon"></div>
    <div class="balloon"></div>
    <div class="balloon"></div>
    <div class="balloon"></div>
    <div class="balloon"></div>
  </div>
  <div class="image-box">
    <img v-if="firstGifShow" class="birthday-gif" src="./assets/gifs/frida_website/5-days.gif"/>
    <div v-if="secondGifShow" class="on">
      <img v-if="secondGifShow"  class="birthday-gif" src="./assets/gifs/frida_website/pasos-proibidos.gif"/>
    </div>
    <div v-if="thirdGifShow">
      <img v-if="thirdGifShow"  class="birthday-gif" src="./assets/gifs/frida_website/no-its-not.gif"/>
    </div>
  </div>
  <div class="background">
    <div class="wrapper">
      <MessageComponent :msg="msg" :msg2="msg2" />
    </div>

    <div class="buttons center">
      <button v-if="!isHidden" class="button-response" v-on:click="changeMessageMentirosa()">¡Si!</button>
      <button v-if="!isHidden" class="button-response" v-on:click="changeMessageWithDaysLeft()">No..</button>
    </div>
    <div v-if="showSecond" class="buttons center ">
      <button v-if="showSecond" class="button-response single-button" v-on:click="changeMessageSecondGif()">Quieres premio consolativo?</button>

    </div>

  </div>
</template>

<style scoped>

/* RAVE LIGHTS START */
body{
  background: black;
}
#rave{
  background: white;
  width: 100%;
  height: 100%;
  position: absolute;
  top: 0;
  left: 0;
}
#raveBtn{
  width: 200px;
  height: 45px;
  background: black;
  margin: 0 auto;
  border-radius: 10px;
  font-family: arial;
  font-weight: bold;
  display: block;
  cursor: pointer;
  text-align: center;
  padding-top: 15px;
  top: 30px;
  position: relative;
}
.on{
  -webkit-animation: raveOn .9s infinite;
}
.off{
  opacity: 0;
}
@-webkit-keyframes raveOn{
  0%{
    opacity: 1;
  }
  100%{
    opacity: 0;
  }
}

/* RAVE LIGHTS */

.single-button{
  width: 100%!important;
  height: auto!important;
}

.button-response{
  width: 50%;
  height: 4rem;
  color: white;
  font-size: 2rem;
  background-color: #FE7F9B;
}

.button-response:hover {
  background-color: #FFB5BB; /* Green */
  color: white;
}

.center{
  margin: auto;
  width: 50%;
  /* border: 3px solid green; */
  padding: 10px;
}

.image-box{
  margin: auto;
  width: 50%;
  /* border: 3px solid green; */
  padding: 10px;
}

header {
  line-height: 1.5;
}

.birthday-gif {
  display: block;
  margin: 0 auto 2rem;
  max-width: 100%;
  height: auto;
  width: auto\9; /* ie8 */
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}


@media only screen and (max-width: 2400px) and (min-width: 1400px)  {
  .balloon-box{
    position:relative;
    line-height: 1;
    padding-top: 2vw;
    margin-left: 2vw;
    margin-right:2vw;
  }
  /* aspect-ratio: 5/6; */
  .balloon {
    display:inline-block;
    width: 8vw;
    aspect-ratio: 5/5.5;
    background:hsl(215,50%,65%);
    border-radius:80%;
    position:relative;
    box-shadow:inset -10px -10px 0 rgba(0,0,0,0.07);
    margin:2vw 5vw;
    transition:transform 0.5s ease;
    z-index:10;
    animation:balloons 4s ease-in-out infinite;
    transform-origin:bottom center;
  }

  .balloon:before {
    content:"▲";
    font-size:1.6vw;
    color:hsl(215,30%,50%);
    display:block;
    text-align:center;
    width:100%;
    position:absolute;
    bottom:-1.1vw;
    z-index:-100;
  }
}


@media only screen and (max-width: 1399px) and (min-width: 0px)  {
.button-response{
  font-size: 1.6rem!important;
}

.balloon-box{
    position:relative;
    line-height: 1;
    padding-top: 2vw;
    margin-left: 2vw;
    margin-right:2vw;
  }
/* aspect-ratio: 5/6; */
.balloon {
  display:inline-block;
  width: 10vw;
  aspect-ratio: 5/6;
  background:hsl(215,50%,65%);
  border-radius:80%;
  position:relative;
  box-shadow:inset -10px -10px 0 rgba(0,0,0,0.07);
  margin:2vw 4.5vw;
  transition:transform 0.5s ease;
  z-index:10;
  animation:balloons 4s ease-in-out infinite;
  transform-origin:bottom center;
}

.balloon:before {
  content:"▲";
  font-size:2.2vw;
  color:hsl(215,30%,50%);
  display:block;
  text-align:center;
  width:100%;
  position:absolute;
  bottom:-1.6vw;
  z-index:-100;
}
}

@keyframes balloons {
  0%,100%{ transform:translateY(0) rotate(-4deg); }
  50%{ transform:translateY(-25px) rotate(4deg); }
}


.balloon:nth-child(2){ background:hsl(245,40%,65%); animation-duration:3.5s; }
.balloon:nth-child(2):before { color:hsl(245,40%,65%);  }

.balloon:nth-child(3){ background:hsl(139,50%,60%); animation-duration:3s; }
.balloon:nth-child(3):before { color:hsl(139,30%,50%);  }

.balloon:nth-child(4){ background:hsl(59,50%,58%); animation-duration:4.5s; }
.balloon:nth-child(4):before { color:hsl(59,30%,52%);  }

.balloon:nth-child(5){ background:hsl(23,55%,57%); animation-duration:5s; }
.balloon:nth-child(5):before { color:hsl(23,44%,46%);  }



</style>
