<script setup lang="ts">
const email = ref("");
const show = ref(false);
const password = ref("");
</script>
<template>
  <div
    class="absolute top-0 left-0 w-screen flex items-center justify-center gap-4 h-screen"
  >
    <div class="w-1/4 overflow-hidden">
      <img
        src="../assets/images/trader.jpg"
        class="h-screen"
        alt=""
        style="width: 700px; height: 100vh !important; object-fit: cover"
      />
    </div>
    <div class="flex w-full items-center justify-center flex-col h-screen">
      <div class="text-5xl font-bold text-primary">
        Welcome back to
        <span class="journaly text-5xl">Journaly</span>
      </div>
      <div
        class="text-center my-10 opacity-70"
        style="margin-top: 1.3rem; margin-bottom: 1.5rem; width: 450px"
      >
        Build your system effortlessly with our powerful yet simple journaling
        platform.
      </div>
      <div class="flex flex-col w-2/3" style="width: 450px">
        <UInput
          v-model="email"
          placeholder="E-mail"
          :ui="{ base: 'peer' }"
          class="w-full mb-4 flex items-center"
          size="xl"
        >
        </UInput>
        <UInput
          v-model="password"
          placeholder="Password"
          :type="show ? 'text' : 'password'"
          :ui="{ trailing: 'pe-1', base: 'peer' }"
          aria-describedby="password-strength"
          class="w-full mb-4"
          size="xl"
        >
          <template #trailing>
            <UButton
              color="neutral"
              variant="link"
              size="sm"
              :icon="show ? 'i-lucide-eye-off' : 'i-lucide-eye'"
              :aria-label="show ? 'Hide password' : 'Show password'"
              :aria-pressed="show"
              aria-controls="password"
              @click="show = !show"
            />
          </template>
        </UInput>
        <UButton
          class="px-9  flex justify-center"
          color="primary"
          variant="solid"
          size="xl"
          >Login</UButton
        >
      </div>
      <div style="margin-top: 0.2rem">
        <div class="text-sm px-5 my-5 font-light">
          <span class="opacity-70">Don't have an account yet?</span>
          <nuxt-link to="/register" class="text-primary"> Register</nuxt-link>
        </div>
      </div>
    </div>
  </div>
</template>
<style>
@import url("https://fonts.googleapis.com/css2?family=Shadows+Into+Light&display=swap");
@import url("https://fonts.googleapis.com/css2?family=Karla:ital,wght@0,200..800;1,200..800&family=Nunito:ital,wght@0,200..1000;1,200..1000&family=Open+Sans:ital,wght@0,300..800;1,300..800&family=Pacifico&family=Satisfy&family=Varela&display=swap");
body {
  font-family: "Open Sans";
}
.journaly {
  font-family: "Shadows Into Light";
}
</style>
