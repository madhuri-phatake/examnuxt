<template>
  <div class="flex items-center justify-center min-h-screen bg-gray-100">
    <div class="px-8 py-6 mt-4 text-left bg-white shadow-lg">
      <p class="text-2xl font-bold m-5">Login</p>

      <div>
        
        <input
          v-model="name"
          aria-label="Enter your email address"
          type="name"
          placeholder="User Name"
          required
          class="text-sm text-gray-base w-full mr-3 py-5 px-4 h-2 border border-gray-200 rounded mb-2"
        />
       
       
        <input
          v-model="password"
          aria-label="Enter your password"
          type="password"
          placeholder="Password"
          class="text-sm text-gray-base w-full mr-3 py-5 px-4 h-2 border border-gray-200 rounded mb-2"
          required
        />
       
        
        <div class="flex justify-center">
          <!-- <NaxtLink v-on:click="login()"
                        class="shadow bg-purple-500 hover:bg-purple-400 focus:shadow-outline focus:outline-none text-white font-bold py-2 px-4 rounded"
                        type="button"
                        >
                        Submit -->
          <button
            @click="login"
            class="shadow bg-purple-500 hover:bg-purple-400 focus:shadow-outline focus:outline-none text-white font-bold py-2 px-4 rounded"
          >
            Submit
          </button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import axios from "axios";
export default {
  name: "login",
  data() {
    return {
      name: "",
      password: "",
      permission: "",
      per: "",
    };
  },
  methods: {
    async login() {
      let per;
      let result = await axios.get(
        `http://localhost:3000/users?email=${this.name}&password=${this.password}`
      );
      if (result.status == 200 && result.data.length > 0) {
        per = result.data[0].permission;
        this.$router.push({ name: "busket", params: { per } });
      } else {
        alert("please enter correct name and password");
      }
    },
  },
};
</script>
