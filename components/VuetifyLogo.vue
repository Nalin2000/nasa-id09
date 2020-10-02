<template>
  <v-img
    src="https://juststickers.in/wp-content/uploads/2019/10/space-saturn.png"
    class="VuetifyLogo"
  />
</template>

<style>
.VuetifyLogo {
  height: 200px;
  width: 200px;
  transform: rotateY(560deg);
  animation: turn 3.5s ease-out forwards 1s;
}

@keyframes turn {
  100% {
    transform: rotateY(0deg);
  }
}
</style>
