<template>
  <div>
    <nav class="flex items-center justify-between flex-wrap bg-blue-700 p-6">
      <div class="flex items-center flex-shrink-0 text-white mr-6">
        <span class="font-semibold text-xl tracking-tight">Welcome!!</span>
      </div>
      <div>
        <NuxtLink
          to="/"
          class="flex justify-endinline-block text-sm px-4 py-2 leading-none border rounded text-white border-white hover:border-transparent hover:text-teal-500 hover:bg-white mt-4 lg:mt-0"
          >LogOut</NuxtLink
        >
      </div>
    </nav>
    <div class="mt-3">
      <h6 align="center">Please choose items to your bucket</h6>
      <div class="grid grid-cols-3 gap-5 mt-14">
        <div
          class="p-6 max-w-sm bg-red-500 rounded-lg border border-gray-200 shadow-md dark:bg-gray-800 dark:border-gray-700"
        >
          <div
            class="apple mb-2 text-2xl text-center font-bold tracking-tight text-gray-900 dark:text-white"
          >
            {{ apple.name }}
          </div>
          <div class="flex flex-1 justify-center p-9 text-4xl">
            {{ apple.count }}
          </div>
          <div class="flex flex-1 justify-center">
            <button
              v-on:click="add"
              class="py-2 px-4 rounded-full h-14 w-14 bg-white text-black mx-1"
            >
              +</button
            ><button
              v-on:click="remove"
              class="py-2 px-4 rounded-full h-14 w-14 bg-white text-black mx-1"
            >
              -
            </button>
          </div>
        </div>
        <div
          class="p-6 max-w-sm bg-yellow-500 rounded-lg border border-gray-200 shadow-md dark:bg-gray-800 dark:border-gray-700"
        >
          <div
            class="orange mb-2 text-2xl text-center font-bold tracking-tight text-gray-900 dark:text-white"
          >
            {{ orange.name }}
          </div>
          <div class="flex flex-1 justify-center p-9 text-4xl">
            {{ orange.count }}
          </div>
          <div class="flex flex-1 justify-center">
            <button
              @click="add1"
              class="py-2 px-4 rounded-full h-14 w-14 bg-white text-black mx-1"
            >
              +</button
            ><button
              v-on:click="remove1"
              class="py-2 px-4 rounded-full h-14 w-14 bg-white text-black mx-1"
            >
              -
            </button>
          </div>
        </div>
        <div
          class="p-6 max-w-sm bg-blue-800 rounded-lg border border-gray-200 shadow-md dark:bg-gray-800 dark:border-gray-700"
        >
          <div
            class="grapes mb-2 text-2xl text-center font-bold tracking-tight text-gray-900 dark:text-white"
          >
            {{ grapes.name }}
          </div>
          <div class="flex flex-1 justify-center p-9 text-4xl">
            {{ grapes.count }}
          </div>
          <div class="flex flex-1 justify-center">
            <button
              v-on:click="add2"
              class="py-2 px-4 rounded-full h-14 w-14 bg-white text-black mx-1"
            >
              +</button
            ><button
              v-on:click="remove2"
              class="py-2 px-4 rounded-full h-14 w-14 bg-white text-black mx-1"
            >
              -
            </button>
          </div>
        </div>
      </div>
    </div>

    <div
      class="flex justify-center items-center border-solid border-2 border-indigo-600 bg-white"
    >
      <div class="flex-1 max-w-2xl p-10">
        <h2 class="text-center p-10 font-bold">Basket Stack</h2>
        <div>
          <h3 v-if="show" class="text-center">No Selected items</h3>
          <div v-else>
            <center>
            <table class="w-64 items-center justify-center border-black">
              <tr
                class=" border-black rounded-full text-center w-10"
                v-for="(basket, index) in basket.slice().reverse()"
                :key="index"
              >
                <td :class="classe[basket]">{{ basket }}</td>
              </tr>
            </table>
            </center>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      apple: {
        name: "Apple",
        count: 10,
        color: "",
      },
      orange: {
        name: "Orange",
        count: 10,
        color: "",
      },
      grapes: {
        name: "Grapes",
        count: 10,
        color: "",
      },
      basket: [],
      classe: {
        Apple: "apple",
        Orange: "orange",
        Grapes: "grapes",
      },
      show: true,
    };
  },
  methods: {
    add() {
      if (this.apple.count > 0) {
        this.apple.count = this.apple.count === 0 ? 0 : this.apple.count - 1;
        this.basket.push(this.apple.name);
        this.show = false;
      } else {
        alert("you already aaded 10 item");
      }
    },
    remove() {
      if (this.basket.at(-1) == this.apple.name) {
        this.apple.count = this.apple.count === 10 ? 10 : this.apple.count + 1;
        this.basket.pop();
      } else {
        alert("You have selected invalid item");
      }
    },
    add1() {
      if (this.orange.count > 0) {
        this.orange.count = this.orange.count === 0 ? 0 : this.orange.count - 1;
        this.basket.push(this.orange.name);
      } else {
        alert("You have selected 10 items");
      }
    },
    remove1() {
      if (this.basket.at(-1) == this.orange.name) {
        this.orange.count =
          this.orange.count === 10 ? 10 : this.orange.count + 1;
        this.basket.pop();
      } else {
        alert("You have selected invalid item ");
      }
    },
    add2() {
      if (this.grapes.count > 0) {
        this.grapes.count = this.grapes.count === 0 ? 0 : this.grapes.count - 1;
        this.basket.push(this.grapes.name);
      } else {
        alert("You have selected 10 items ");
      }
    },
    remove2() {
      console.warn(this.basket.at(-1));
      if (this.basket.at(-1) == this.grapes.name) {
        this.grapes.count =
          this.grapes.count === 10 ? 10 : this.grapes.count + 1;
        this.basket.pop();
      } else {
        alert("You have selected invalid item ");
      }
    },
  },
};
</script>

<style scoped>
.apple {
  background-color: rgb(239, 68, 68);
}
.orange {
  background-color: rgb(234, 179, 8);
}
.grapes {
  background-color: rgb(30, 64, 175);
}
</style>
