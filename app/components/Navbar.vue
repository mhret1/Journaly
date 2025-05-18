<template>
  <div
    class="flex fixed font-light top-0 left-0 w-screen overflow-x-hidden justify-between py-10 px-32 items-center"
  >
    <div class="navbar__title text-4xl">Journaly</div>
    <div class="flex items-center">
      <div class="mx-5">
        <nuxt-link to="#" class="">Features</nuxt-link>
        <nuxt-link to="#" class="mx-5">About</nuxt-link>
        <nuxt-link to="#">Contact</nuxt-link>
      </div>

      <nuxt-link to="login"
        ><UButton label="Log In" size="lg" class="mr-5 navbar__button"
      /></nuxt-link>
      <UButton label="Register" variant="outline" size="lg" />
    </div>
  </div>
</template>
<style>
@import url("https://fonts.googleapis.com/css2?family=Shadows+Into+Light&display=swap");
@import url("https://fonts.googleapis.com/css2?family=Karla:ital,wght@0,200..800;1,200..800&family=Nunito:ital,wght@0,200..1000;1,200..1000&family=Open+Sans:ital,wght@0,300..800;1,300..800&family=Pacifico&family=Satisfy&family=Varela&display=swap");
body {
  font-family: "Open Sans";
}
.navbar__title {
  font-family: "Shadows Into Light";
  font-weight: bold;
}
button {
  cursor: pointer;
}
</style>
