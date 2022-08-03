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
                >LogOut</NuxtLink>
                
            </div>
            </nav>
            <div class="grid grid-cols-3 gap-5 mt-14">
            <div
                class="p-6 max-w-sm bg-red-800 rounded-lg border border-gray-200 shadow-md dark:bg-gray-800 dark:border-gray-700"
            >
                <a href="#">
                <h5
                    class="mb-2 text-2xl text-center font-bold tracking-tight text-gray-900 dark:text-white"
                >
                    {{apple.name}}
                </h5>
                </a>
                <div class="flex flex-1 justify-center p-9 text-4xl">{{ apple.count }}</div>
                <div class="flex flex-1 justify-center">
                <button
                    @click="add"
                    class="py-2 px-4 rounded-full h-14 w-14 bg-white text-black mx-1"
                    
                >
                    +
                </button>
                <button
                    @click="remove"
                    class="py-2 px-4 rounded-full h-14 w-14 bg-white text-black mx-1"
                    
                >
                    -
                </button>
                </div>
            </div>
            <div
                class="p-6 max-w-sm bg-yellow-500 rounded-lg border border-gray-200 shadow-md dark:bg-gray-800 dark:border-gray-700"
            >
                <a href="#">
                <h5
                    class="mb-2 text-2xl text-center font-bold tracking-tight text-gray-900 dark:text-white"
                >
                    {{orange.name}}
                </h5>
                </a>
                <div class="flex flex-1 justify-center p-9 text-4xl">
            {{ orange.count }}
                </div>
                <div class="flex flex-1 justify-center">
                <button
                    @click="add1"
                    class="py-2 px-4 rounded-full h-14 w-14 bg-white text-black mx-1"
                    
                >
                    +
                </button>
                <button
                    @click="remove1"
                    class="py-2 px-4 rounded-full h-14 w-14 bg-white text-black mx-1"
                    
                >
                    -
                </button>
                </div>
            </div>
            <div
                class="p-6 max-w-sm bg-blue-500 rounded-lg border border-gray-200 shadow-md dark:bg-gray-800 dark:border-gray-700"
            >
                <a href="#">
                <h5
                    class="mb-2 text-2xl text-center font-bold tracking-tight text-gray-900 dark:text-white"
                >
                    {{grapes.name}}
                </h5>
                </a>
                <div class="flex flex-1 justify-center p-9 text-4xl">
                {{ grapes.count }}
                </div>
                <div class="flex flex-1 justify-center">
                <button
                    @click="add2"
                    class="py-2 px-4 rounded-full h-14 w-14 bg-white text-black mx-1"
                
                >
                    +
                </button>
                <button
                    @click="remove2"
                    class="py-2 px-4 rounded-full h-14 w-14 bg-white text-black mx-1"
                
                >
                    -
                </button>
                </div>
            </div>
            </div>
            <div class="flex justify-center items-center border-solid border-2 border-indigo-600 bg-white">
                <div class="flex-1 max-w-4xl p-16">
                <h2 class="text-center  p-10 font-bold">Basket Stack</h2>
                <div>
                    <h3 v-if="show" class="text-center ">No Selected items</h3>
                    <!-- <div >
                        <table>
                            <tr v-if="showApple">
                                <div class="col-span-2 text-center text-white p-2  bg-red-500 border-1-8 border-teal-400 rounded-md shadow-md space-y-2">{{ basketApple.join(",") }}</div>
                            </tr>
                        </table>
                        <table>
                            <tr v-if="showOrange">
                            <div class="col-span-2 text-center text-white p-2 bg-orange-500 border-1-8 border-teal-400 rounded-md shadow-md space-y-2">{{ basketOrange.join(",") }}</div>
                            </tr>
                        </table>
                        <table>
                            <tr v-if="showGrapes">
                                <div class="col-span-2 text-center text-white p-2 bg-blue-500 border-1-8 border-teal-400 rounded-md shadow-md space-y-2">{{ basketGrapes.join(",") }}</div>

                            </tr>
                        </table>
                    </div> -->
                    <table class="w-64  items-center justify-center">
                    <tr class="border-solid border-2 border-indigo-600 w-10" v-for="(basket, index) in basket" :key="index">
            <td>{{basket}}</td>
            </tr></table>
                    </div>
                    </div>
        
            
            <!-- <div class="flex justify-center items-center min-w-0 bg-white">
            <div class="flex-1 max-w-4xl p-16">
                <h2 class="text-center p-10 font-bold">Basket Stack</h2>
                <div
                class="col-span-2 text-center text-white p-4 pr-6 bg-orange-500 border-1-8 border-teal-400 rounded-md shadow-md space-y-2"
                >
                {{  }} Apple
                </div>
                <div
                class="col-span-2 text-center text-white p-4 pr-6 bg-red-500 border-1-8 border-teal-400 rounded-md shadow-md space-y-2"
                >
                {{  }} Orange
                </div>
                <div
                class="col-span-2 text-center text-white p-4 pr-6 bg-blue-500 border-1-8 border-teal-400 rounded-md shadow-md space-y-2"
                >
            {{  }} Grape
                </div>
            </div>
            </div> -->



            <!-- <div class="m-8">
        <div>
            <h4>Basket stack</h4>
        </div>
        <div>{{ basket.join(",") }}</div>
        </div>  -->


        </div> 
        </div>
        </template>

        
    
    <script>
    export default {
        data() {
            return {
                "apple": {
                    name: "Apple",
                    count: 10,
                    color: " #FF0000",
                
                },
                "orange": {
                    name: "Orange",
                    count: 10,
                    color: "#FF8000",
                
                },
                "grapes": {
                    name: "Grapes",
                    count: 10,
                    color: "#800080",
                
                },
                show:true,
                showApple:false,
                showOrange:false,
                showGrapes:false,
                basket: [],
                basketApple: [],
                basketOrange: [],
                basketGrapes: [],
            }
        },
        methods: {
            add() {
                this.showApple = true;
                if (this.apple.count > 0) {
                    this.apple.count = this.apple.count === 0 ? 0 : this.apple.count - 1;
                    this.basketApple.push(this.apple.name)
                    this.show=false
                }
                else {
                    alert("you already aaded 10 item")
                }
            },
            remove() {
                if (this.basketApple.at(-1) == this.apple.name) {
                    this.apple.count = this.apple.count === 10 ? 10 : this.apple.count + 1;
                    this.basketApple.pop()
                }
                else {
                    alert("You have selected invalid item")
                }
            },
            add1() {
                this.showOrange = true;
                if (this.orange.count > 0) {
                    this.orange.count = this.orange.count === 0 ? 0 : this.orange.count - 1;
                    this.basketOrange.push(this.orange.name)
                }
                else {
                    alert("You have selected invalid item")
                }
            },
            remove1() {
                
                if (this.basketOrange.at(-1) == this.orange.name) {
                    this.orange.count = this.orange.count === 10 ? 10 : this.orange.count + 1;
                    this.basketOrange.pop()
                }
                else {
                    alert("You have selected invalid item ")
                }
            },
            add2() {
                this.showGrapes = true;
                if (this.grapes.count > 0) {
                    this.grapes.count = this.grapes.count === 0 ? 0 : this.grapes.count - 1;
                    this.basketGrapes.push(this.grapes.name)
                }
                else {
                    alert("You have selected invalid item ")
                }
            },
            remove2() {
                console.warn(this.basket.at(-1))
                if (this.basketGrapes.at(-1) == this.grapes.name) {
                    this.grapes.count = this.grapes.count === 10 ? 10 : this.grapes.count + 1;
                    this.basketGrapes.pop()
                }
                else {
                    alert("You have selected invalid item ")
                }
            },
            showAppleData(){
                this.showApple = true;
            },
            showOrangeData(){
                this.showOrange = true;
            },
            showGrapesData(){
                this.showGrapes = true;
            },
        }
    }
    </script>