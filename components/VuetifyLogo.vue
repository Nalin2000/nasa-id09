<template>
  <v-img
    src="https://media.giphy.com/media/5h9hhfCzYF9x9eF1gf/giphy.gif"
    class="VuetifyLogo"
  />
</template>

<style>
.VuetifyLogo {
  height: 250px;
  width: 250px;
  transform: rotateY(560deg);
  animation: turn 3.5s ease-out forwards 1s;
}

@keyframes turn {
  100% {
    transform: rotateY(0deg);
  }
}
</style>
