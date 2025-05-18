<script setup>
const auth = useAuth();
const { status, data: session } = auth;

const handleLogout = async () => {
  try {
    await auth.signOut();
  } catch (error) {
    console.error("Logout error:", error);
  }
};
</script>

<template>
  <div>
    <p v-if="status === 'authenticated'">
      Logged in as {{ session?.user?.email }}
    </p>
    <button @click="handleLogout">Logout</button>
  </div>
</template>
