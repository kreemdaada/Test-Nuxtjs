<template>
  <div class="flex items-center justify-center min-h-screen bg-gray-100">
    <div class="w-96 bg-white p-8 shadow-lg rounded-lg">
      <h1 class="text-3xl font-semibold mb-6">Login</h1>
      <form @submit.prevent="login">
        <input v-model="loginData.email" type="email" placeholder="E-Mail" class="input" />
        <input v-model="loginData.password" type="password" placeholder="Password" class="input" />
        <button type="submit" class="button-blue">Log In</button>
      </form>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue';

const showRegistrationForm = ref(false);
const loginData = ref({
  email: '',
  password: '',
});

const showRegisterForm = () => {
  showRegistrationForm.value = true;
};

const login = () => {
  console.log('Login data:', loginData.value);
  // Perform login logic using loginData.email and loginData.password
};

</script>

<style scoped>
.input {
  @apply border rounded p-2 mb-4 w-full text-sm focus:outline-none focus:border-blue-300;
}

.button-blue {
  @apply bg-blue-500 text-white py-2 px-4 rounded-md hover:bg-blue-600 focus:outline-none focus:ring focus:border-blue-300;
}

.button-blue:hover {
  @apply bg-blue-600;
}
</style>
