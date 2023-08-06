<template>
  <div class="flex items-center justify-center min-h-screen bg-gray-100">
    <div class="w-96 bg-white p-8 shadow-lg rounded-lg">
      <h1 class="text-3xl font-semibold mb-6">Login</h1>
      <form>
        <div class="mb-4">
          <label for="email" class="block text-sm font-medium text-gray-700">E-Mail</label>
          <input
            id="email"
            type="email"
            class="mt-1 focus:ring focus:border-blue-300 block w-full shadow-sm sm:text-sm border-gray-300 rounded-md"
          />
        </div>
        <div class="mb-4">
          <label for="password" class="block text-sm font-medium text-gray-700">Password</label>
          <input
            id="password"
            type="password"
            class="mt-1 focus:ring focus:border-blue-300 block w-full shadow-sm sm:text-sm border-gray-300 rounded-md"
          />
        </div>
        <div class="mt-6">
          <button
            type="submit"
            class="w-full bg-blue-500 text-white py-2 px-4 rounded-md hover:bg-blue-600 focus:outline-none focus:ring focus:border-blue-300"
          >
            Log In
          </button>
        </div>
      </form>
      <div class="mt-6">
        <p class="text-gray-700">Not registered yet?</p>
        <button
          type="button"
          class="w-full bg-green-500 text-white py-2 px-4 rounded-md mt-2 hover:bg-green-600 focus:outline-none focus:ring focus:border-green-300"
          @click="showRegisterForm"
        >
          Register
        </button>
      </div>
      <!-- Registration form (hidden by default) -->
      <form v-if="showRegistrationForm" class="mt-6">
        <div class="mb-4">
          <label for="firstName" class="block text-sm font-medium text-gray-700">First Name</label>
          <input
            id="firstName"
            type="text"
            class="mt-1 focus:ring focus:border-blue-300 block w-full shadow-sm sm:text-sm border-gray-300 rounded-md"
          />
        </div>
        <div class="mb-4">
          <label for="lastName" class="block text-sm font-medium text-gray-700">Last Name</label>
          <input
            id="lastName"
            type="text"
            class="mt-1 focus:ring focus:border-blue-300 block w-full shadow-sm sm:text-sm border-gray-300 rounded-md"
          />
        </div>
        <div class="mb-4">
          <label for="regEmail" class="block text-sm font-medium text-gray-700">E-Mail</label>
          <input
            id="regEmail"
            type="email"
            class="mt-1 focus:ring focus:border-blue-300 block w-full shadow-sm sm:text-sm border-gray-300 rounded-md"
          />
        </div>
        <div class="mb-4">
          <label for="regPassword" class="block text-sm font-medium text-gray-700">Password</label>
          <input
            id="regPassword"
            type="password"
            class="mt-1 focus:ring focus:border-blue-300 block w-full shadow-sm sm:text-sm border-gray-300 rounded-md"
          />
        </div>
        <div class="mb-4">
          <label for="confirmPassword" class="block text-sm font-medium text-gray-700">Confirm Password</label>
          <input
            id="confirmPassword"
            type="password"
            class="mt-1 focus:ring focus:border-blue-300 block w-full shadow-sm sm:text-sm border-gray-300 rounded-md"
          />
        </div>
        <div class="mt-6">
          <button
            type="submit"
            class="w-full bg-green-500 text-white py-2 px-4 rounded-md hover:bg-green-600 focus:outline-none focus:ring focus:border-green-300"
          >
            Register
          </button>
        </div>
      </form>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      showRegistrationForm: false,
    };
  },
  methods: {
    showRegisterForm() {
      this.showRegistrationForm = true;
    },
  },
};
</script>
