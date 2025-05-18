<script setup lang="ts">
const email = ref("");
const firstName = ref("");
const lastName = ref("");

const show = ref(false);
const password = ref("");

function checkStrength(str: string) {
  const requirements = [
    { regex: /.{8,}/, text: "At least 8 characters" },
    { regex: /\d/, text: "At least 1 number" },
    { regex: /[a-z]/, text: "At least 1 lowercase letter" },
    { regex: /[A-Z]/, text: "At least 1 uppercase letter" },
  ];

  return requirements.map((req) => ({
    met: req.regex.test(str),
    text: req.text,
  }));
}

const strength = computed(() => checkStrength(password.value));
const score = computed(() => strength.value.filter((req) => req.met).length);

const color = computed(() => {
  if (score.value === 0) return "neutral";
  if (score.value <= 1) return "error";
  if (score.value <= 2) return "warning";
  if (score.value === 3) return "warning";
  return "success";
});

const text = computed(() => {
  if (score.value === 0) return "Enter a password";
  if (score.value <= 2) return "Weak password";
  if (score.value === 3) return "Medium password";
  return "Strong password";
});
</script>
<template>
  <div
    class="absolute top-0 left-0 w-screen flex items-center justify-center gap-4 h-screen"
  >
    <div class="w-1/4 overflow-hidden">
      <img
        src="../assets/images/trader-2.jpg"
        class="h-screen"
        alt=""
        style="width: 550px; height: 100vh !important; object-fit: cover"
      />
    </div>
    <div class="flex w-full items-center justify-center flex-col h-screen">
      <div class="text-5xl font-bold text-primary">
        Start your journey
        <span class="journaly text-5xl">Journaly</span>
      </div>
      <div
        class="text-center font-light my-10 opacity-70"
        style="margin-top: 1.3rem; margin-bottom: 1.5rem; width: 450px"
      >
        Build your system effortlessly with our powerful yet simple journaling
        platform.
      </div>
      <div class="flex flex-col w-2/3" style="width: 450px">
        <UFormField class="w-full">
          <UInput
            v-model="firstName"
            placeholder="First Name"
            :ui="{ base: 'peer' }"
            class="w-full mb-4 flex items-center"
            size="xl"
          >
          </UInput>
          <UInput
            v-model="lastName"
            placeholder="Last Name"
            :ui="{ base: 'peer' }"
            class="w-full mb-4 flex items-center"
            size="xl"
          >
          </UInput>
          <UInput
            v-model="email"
            placeholder="E-mail"
            :ui="{ base: 'peer' }"
            class="w-full flex items-center"
            size="xl"
          >
          </UInput>
        </UFormField>
        <PasswordInput />
        <UButton
          class="px-9 mt-1 flex justify-center"
          color="primary"
          variant="solid"
          size="xl"
          >Register</UButton
        >
      </div>
      <div style="margin-top: 0.2rem">
        <div class="text-sm px-5 my-5 font-light">
          <span class="opacity-70">Already have an account?</span>
          <nuxt-link to="/login" class="text-primary"> Login</nuxt-link>
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
