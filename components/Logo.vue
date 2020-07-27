<template>
  <div class="text-center NuxtLogo">
    <img src="~assets/img/logo-black.png" alt="Moon Logo">
  </div>
</template>
<style scoped>
.NuxtLogo {
  animation: 1s appear;
  margin: auto;
}

@keyframes appear {
  0% {
    opacity: 0;
  }
  100% {
    opacity: 1;
  }
}
img {
  width: 300px;
  margin: 0 auto;
}
</style>
