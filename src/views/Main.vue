<template>
  <div class=" start-page row justify-content-center">
    <div class="col-md-6 col-sm-12">
      <header>
        <!-- https://storage.googleapis.com/ngongbabyandcoder.appspot.com/Love.png -->
        <img id="banner" class="w-100" src="https://storage.googleapis.com/ngongbabyandcoder.appspot.com/banner.png"
          alt="banner">
      </header>
      <span id="items" class="d-flexx">
        <img id="leftwing" src="https://storage.googleapis.com/ngongbabyandcoder.appspot.com/leftwing.png" alt="wing">
        <span id="letter" class="d-flex align-items-center justify-content-center" @click="test()">
          <img id="heart" src="https://storage.googleapis.com/ngongbabyandcoder.appspot.com/heart.png" alt="heart">
          <img id="envelope" src="https://storage.googleapis.com/ngongbabyandcoder.appspot.com/envelop.png" alt="letter">
        </span>
        <img id="rightwing" src="https://storage.googleapis.com/ngongbabyandcoder.appspot.com/rightwing.png" alt="wing">
      </span>
    </div>
  </div>
</template>

<script setup lang="ts">
import router from '@/router';

const test = () => {
  router.push({
    name: 'letter',
  })
}
</script>

<style>
.start-page {
  background: mistyrose;
  height: 100vh;
}

#banner {
  padding-top: 10%;
  display: block;
  margin-left: auto;
  margin-right: auto;
}

#items {
  display: grid;
  grid-template-columns: .5fr .5fr .5fr;
  grid-template-rows: auto;
  grid-template-areas:
    "lw en rw";
}

#leftwing {
  grid-area: lw;
  width: 100%;
  direction: rtl;
  padding: 0 10px 20px 10px;
  animation: wingTopFlap1 0.5s infinite;
  /* transform: rotate(-12deg) rotate3d(0, 0, 0, 10deg); */
}

#rightwing {
  grid-area: rw;
  width: 100%;
  padding: 0 10px 20px 10px;
  animation: wingTopFlap2 1s infinite;
}

@keyframes flap1 {
  0% {
    transform: rotate(10deg) translate(0, 15px);
  }

  50% {
    transform: rotate(5deg) translate(0, 15px);
  }
}

@keyframes wingTopFlap1 {

  0%,
  100% {
    transform: rotate(2deg) rotate3d(0, 0, 0, 10deg);
  }

  50% {
    transform: rotate(2deg) rotate3d(0, 1, 0, 10deg);
  }
}

@keyframes wingTopFlap2 {

  0%,
  100% {
    transform: rotate(2deg) rotate3d(0, 0, 0, 10deg);
  }

  50% {
    transform: rotate(2deg) rotate3d(0, 1, 0, 10deg);
  }
}

@keyframes flap2 {
  0% {
    transform: rotate(-10deg) translate(0, 15px);
  }

  50% {
    transform: rotate(-5deg) translate(0, 15px);
  }

  75% {
    transform: rotate(-10deg) translate(0, 15px);
  }
}


#letter {
  padding-top: 10%;
  grid-area: en;
  position: relative;
  z-index: 99;
  cursor: pointer;
}

#heart {
  position: absolute;
  max-width: 60%;
  width: 60%;
  z-index: 100;
  animation: heart 1s infinite;
}

@keyframes heart {
  0% {
    transform: scale(.8) translate(0, 0);
  }

  50% {
    transform: scale(.90) translate(0, 8px);
  }

  100% {
    transform: scale(.8);
  }
}

#envelope {
  max-width: 100%;
  animation: floaty 1s infinite;
}

@keyframes floaty {
  0% {
    transform: translate(0, 0);
  }

  50% {
    transform: translate(0, 12px);
  }
}
</style>