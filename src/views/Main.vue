<template>
  <main>
    <header>
      <img id="banner" :src="banner" alt="banner">
    </header>
    <span id="items">
      <img id="rightwing" :src="rightwing" alt="wing">
      <img id="leftwing" :src="leftwing" alt="wing">
      <span id="letter">
        <a href="#"><img id="heart" :src="heart" alt="heart"></a>
        <img id="envelope" :src="envelop" alt="letter">
      </span>
    </span>
  </main>
</template>

<script setup lang="ts">
import banner from "@/assets/images/banner.png"
import rightwing from "@/assets/images/rightwing.png"
import leftwing from "@/assets/images/leftwing.png"
import heart from "@/assets/images/heart.png"
import envelop from "@/assets/images/envelop.png"
</script>

<style>
body {
  background: mistyrose;

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

#rightwing {
  max-width: 80%;
  /* animation: flap1 1s infinite; */
  grid-area: rw;
}

@keyframes flap1 {
  0% {
    transform: rotate(10deg) translate(0, 15px);
  }

  50% {
    transform: rotate(5deg) translate(0, 15px);
  }
}

#leftwing {
  max-width: 80%;
  grid-area: lw;
  padding-left: 20%;
  padding-top: 2%;
  /* animation: flap2 1s infinite; */
}

@keyframes flap2 {
  0% {
    transform: rotate(-10deg) translate(0, 15px);
  }

  50% {
    transform: rotate(-5deg) translate(0, 15px);
  }
}


#letter {
  padding-top: 10%;
  grid-area: en;
}

#heart {
  max-width: 10%;
  position: absolute;
  z-index: 1;
  padding-left: 13.5%;
  padding-top: 8%;
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