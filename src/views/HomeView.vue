<script setup>
import SquareNoAnimation from "../components/SquareNoAnimation.vue";
</script>

<template>
  <main>
    <div class="container">
      <SquareNoAnimation
        v-for="n in 90"
        :key="`square1-${n}`"
        :style="{
          // transform: `scale(${8 - n * 0.1}) rotate(w{n * 12416}deg) translate(${n * 1}px, ${n * 1}px)`,
          transform: `scale(${9.5 - n * 0.1}) rotate(${n * -2304}deg) translate(${n * 1}px, ${n * 1}px)`,
          // transform: `scale(${8.2 - n * 0.1}) rotate(${n * 12421}deg) translate(${n * 1}px, ${n * 1}px)`,
          // zIndex: 80 - n, // Higheer n renders below lower n

          // O G
          // transform: `scale(${8 - n * 0.1}) rotate(${n * -2020202}deg) translate(${n * 1}px, ${n * 1}px)`,
        }"
        :class="{ square: true }"
      />

      <!-- <SquareNoAnimation
        v-for="n in 60"
        :key="`square2-${n}`"
        :style="{
          transform: `scale(${6 - n * 0.1}) rotate(${n * 12421}deg) translate(${n * 1}px, ${n * 1}px)`,
          transform: `scale(${8 - n * 0.1}) rotate(${n * -2400}deg) translate(${n * 1}px, ${n * 1}px)`,
        }"
        :class="{ square2: true }"
      /> -->

      <!-- <SquareNoAnimation
        v-for="n in 60"
        :key="`square3-${n}`"
        :style="{
          transform: `scale(${6 - n * 0.1}) rotate(${n * 12421}deg) translate(${n * 1}px, ${n * 1}px)`,
        }"
        :class="{ square3: true }"
      /> -->
    </div>
  </main>
</template>

<style scoped>
@keyframes pulseOpacity {
  0%,
  100% {
    opacity: 1;
  }
  50% {
    opacity: 0.8;
  }
}
@keyframes pulseEffect {
  0%,
  100% {
    opacity: 1;
  }
  50% {
    opacity: 0.7;
    transform: scale(16);
  }
}

.square {
  animation: pulseEffect 600s ease-in-out infinite;
}
@keyframes square-animation {
  0% {
    background-size: 400% 400%;
  }
  50% {
    background-size: 200% 200%;
  }
  100% {
    background-size: 400% 100%;
  }
}
/* 
.square:hover {
  animation: pulseOpacity .5s ease-in-out ;
} */

@keyframes fadeIn {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}
.square3 {
  position: absolute;
  top: 75%;
  left: 80%;
  transform-origin: center;
  /* padding: 30px; */
  opacity: 1;
  background: linear-gradient(135deg, #fcb04595, #fd1d1d7c 40%, #8463ae94);
  background-size: 100% 100%;
  animation:
    /* square-animation 3s ease-in-out infinite, */ fadeIn 2s
    ease-in forwards;
  transition:
    transform 0.5s ease,
    background 0.5s ease,
    background-size 0.7s ease,
    box-shadow 0.5s ease;
  height: 20px;
  width: 20px;
}
.square2 {
  position: absolute;
  top: 20%;
  left: 20%;
  transform-origin: center;
  /* padding: 30px; */
  opacity: 1;
  /* background: linear-gradient(135deg, #fcb04595, #fd1d1d7c 40%, #8463ae94); */
  background-size: 100% 100%;
  animation:
    square-animation 3s ease-in-out infinite,
    fadeIn 2s ease-in forwards;
  transition:
    transform 0.5s ease,
    background 0.5s ease,
    background-size 0.7s ease,
    box-shadow 0.5s ease;
  height: 20px;
  width: 20px;
}
.square {
  position: absolute;
  /* top: 50%; */
  /* left: 50%; */
  transform-origin: center;
  padding: 20px;
  opacity: 1;
  background: linear-gradient(135deg, #fcb04595, #fd1d1d7c 40%, #8463ae94);
  /* background: linear-gradient(
    135deg,
    rgba(252, 176, 69, 0.4),
    rgba(253, 29, 29, 0.3) 40%,
    rgba(132, 99, 174, 0.4)
  ); */
  background-color: rgba(255, 246, 246, 0.187);
  background-size: 60% 100%;

  background-size: 100% 100%;

  /* animation: square-animation 10s ease-in-out infinite; */
  /* fadeIn 2s ease-in forwards; */
  transition:
    transform 0.5s ease,
    background 0.5s ease,
    background-size 0.7s ease,
    box-shadow 0.5s ease;
  height: 30px;
  width: 30px;
  /* box-shadow: 0 2px 10px rgba(255, 255, 255, 0.5); */
}

.container {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
  /* cursor: pointer; */
}

main {
  width: 100%;
  height: 100vh;
  font-family: "IBM Plex Mono";
  color: #333;
  background: linear-gradient(90deg, #8463ae94, #fd1d1d7c 20%, #fcb04595);
  background-size: 300% 300%;
  /* animation: gradient-shift 50s ease-in-out infinite; */
}

@keyframes gradient-shift {
  0%,
  100% {
    background-position: 0% 0%;
  }
  50% {
    background-position: 100% 100%;
  }
}

main::before {
  content: "";
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-size: cover;
  background-position: center;
  opacity: 0.45;
  z-index: -1;
}
</style>
