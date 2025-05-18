<style scoped>
.glow {
  position: absolute;
  width: 400px;
  height: 400px;
  border-radius: 50%;
  background: radial-gradient(circle, #00d492, #a173ff);
  opacity: 0.6;
  filter: blur(120px);
  animation: moveGlow 20s infinite ease-in-out alternate;
}

.glow:nth-child(2) {
  top: 50%;
  left: 60%;
  background: radial-gradient(circle, #00d492, #b490ca);
  animation-delay: 5s;
}

@keyframes moveGlow {
  0% {
    top: 20%;
    left: 30%;
  }
  100% {
    top: 60%;
    left: 70%;
  }
}
</style>
<template>
  <div class="flex flex-col items-center justify-center gap-4 h-screen">
    <Navbar />
    <div class="glow"></div>
    <div class="glow"></div>
    <div class="flex items-center px-32">
      <div>
        <div class="text-5xl font-extrabold leading-14 text-primary">
          Simplify your tradig journey with Journaly
        </div>
        <div class="opacity-70 font-light my-8">
          Easily track and analyze your trades with our intuitive journaling
          platform.
        </div>
        <UButton
          label="Get started"
          class="mr-5 px-10 py-4 navbar__button"
          to="/register"
        />
      </div>
      <div>
        <img style="width: 675px" src="../assets/svg/trader.svg" alt="" />
      </div>
    </div>
  </div>
</template>
