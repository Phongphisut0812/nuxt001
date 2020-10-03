<template>
  <img
    class="VuetifyLogo"
    alt="Vuetify Logo"
    src="https://cdn.dribbble.com/users/418188/screenshots/3819319/logo_animation_tubik_design.gif"
  />
</template>

<style>
.VuetifyLogo {
  height: 250px;
  transform: rotateY(560deg);
  animation: turn 3.5s ease-out forwards 1s;
}

@keyframes turn {
  100% {
    transform: rotateY(0deg);
  }
}
</style>
