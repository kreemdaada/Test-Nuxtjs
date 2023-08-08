<template>
    <div class="flex items-center justify-center min-h-screen bg-gray-100">
      <div class="w-96 bg-white p-8 shadow-lg rounded-lg">
        <h1 class="text-3xl font-semibold mb-6">Register</h1>
        <form @submit.prevent="register">
          <input v-model="registrationData.firstName" type="text" placeholder="First Name" class="input" />
          <input v-model="registrationData.lastName" type="text" placeholder="Last Name" class="input" />
          <input v-model="registrationData.email" type="email" placeholder="E-Mail" class="input" />
          <input v-model="registrationData.password" type="password" placeholder="Password" class="input" />
          <input v-model="registrationData.confirmPassword" type="password" placeholder="Confirm Password" class="input" />
          <button type="submit" class="button-blue">Register</button>
        </form>
      </div>
    </div>
  </template>
  
  <script setup>
  import { ref } from 'vue';
  
  const showRegistrationForm = ref(false);
  const registrationData = ref({
    firstName: '',
    lastName: '',
    email: '',
    password: '',
    confirmPassword: '',
  });
  
  const showLoginForm = () => {
    showRegistrationForm.value = false;
  };
  
  const register = () => {
    console.log('Registration data:', registrationData.value);
    // Perform registration logic using registrationData
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
  