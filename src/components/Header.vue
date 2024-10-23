<script setup>
import { ref, watch } from "vue";
import { Dialog, DialogPanel } from "@headlessui/vue";
import {
  Bars3Icon,
  XMarkIcon,
  UserCircleIcon,
} from "@heroicons/vue/24/outline";

const navigation = [
  { name: "Equipment", href: "#" },
  { name: "About us", href: "#" },
  { name: "Blog", href: "#" },
];

const mobileMenuOpen = ref(false);
const aboveFold = ref(true);

const scrollThreshold = window.innerHeight / 2;
window.addEventListener("scroll", () => {
  const scrolledPastFold = document.documentElement.scrollTop > scrollThreshold;
  aboveFold.value = !scrolledPastFold;
});
</script>

<template>
  <div class="bg-white">
    <header
      v-if="aboveFold"
      class="inset-x-0 top-0 z-50 fixed transition-opacity ease-in"
      v-motion-fade-visible
    >
      <nav
        class="flex items-center justify-between p-6 lg:px-8"
        aria-label="Global"
      >
        <div class="flex lg:flex-1">
          <a href="#" class="-m-1.5 p-1.5">
            <span class="sr-only">Your Company</span>
            <h1 class="h-8 uppercase font-bold">Huy</h1>
          </a>
        </div>
        <div class="flex lg:hidden">
          <button
            type="button"
            class="-m-2.5 inline-flex items-center justify-center rounded-md p-2.5"
            @click="mobileMenuOpen = true"
          >
            <span class="sr-only">Open main menu</span>
            <Bars3Icon class="h-6 w-6" aria-hidden="true" />
          </button>
        </div>
        <div class="hidden lg:flex lg:gap-x-12">
          <a
            v-for="item in navigation"
            :key="item.name"
            :href="item.href"
            class="text-sm font-semibold leading-6"
            >{{ item.name }}</a
          >
        </div>
        <div class="hidden lg:flex lg:flex-1 lg:justify-end">
          <a href="#" class="text-sm font-semibold leading-6">
            <UserCircleIcon class="h-6 w-6 inline" aria-hidden="true" />

            Account</a
          >
        </div>
      </nav>
      <Dialog
        class="lg:hidden"
        @close="mobileMenuOpen = false"
        :open="mobileMenuOpen"
      >
        <div class="fixed inset-0 z-50" />
        <DialogPanel
          class="fixed inset-y-0 end-0 z-50 w-full overflow-y-auto bg-black px-6 py-6 sm:max-w-sm sm:ring-1 sm:ring-gray-900/10"
        >
          <div class="flex items-center justify-between">
            <a href="#" class="-m-1.5 p-1.5">
              <span class="sr-only">Your Company</span>
              <h1 class="h-8">Huy</h1>
            </a>
            <button
              type="button"
              class="-m-2.5 rounded-md p-2.5"
              @click="mobileMenuOpen = false"
            >
              <span class="sr-only">Close menu</span>
              <XMarkIcon class="h-6 w-6" aria-hidden="true" />
            </button>
          </div>
          <div class="mt-6 flow-root">
            <div class="-my-6 divide-y divide-white">
              <div class="space-y-2 py-6">
                <a
                  v-for="item in navigation"
                  :key="item.name"
                  :href="item.href"
                  class="-mx-3 block rounded-lg px-3 py-2 text-base font-semibold leading-7 hover:bg-gray-50 hover:text-black transition-colors"
                  >{{ item.name }}</a
                >
              </div>
              <div class="py-6">
                <a
                  href="#"
                  class="flex sm:hidden items-center space-x-1 -mx-3 rounded-lg px-3 py-2.5 text-base font-semibold leading-7 hover:bg-gray-50 hover:text-black transition-colors"
                >
                  <svg
                    xmlns="http://www.w3.org/2000/svg"
                    x="0px"
                    y="0px"
                    width="100"
                    height="100"
                    viewBox="0,0,256,256"
                    class="w-6 h-6 inline"
                  >
                    <g
                      fill="#ffffff"
                      fill-rule="nonzero"
                      stroke="none"
                      stroke-width="1"
                      stroke-linecap="butt"
                      stroke-linejoin="miter"
                      stroke-miterlimit="10"
                      stroke-dasharray=""
                      stroke-dashoffset="0"
                      font-family="none"
                      font-weight="none"
                      font-size="none"
                      text-anchor="none"
                      style="mix-blend-mode: normal"
                    >
                      <g transform="scale(5.33333,5.33333)">
                        <path
                          d="M16.5,5c-6.33361,0 -11.5,5.16639 -11.5,11.5v15c0,6.33276 5.16621,11.5 11.5,11.5h15c6.33294,0 11.5,-5.16706 11.5,-11.5v-15c0,-6.33379 -5.16724,-11.5 -11.5,-11.5zM16.5,8h15c4.71124,0 8.5,3.78779 8.5,8.5v15c0,4.71106 -3.78894,8.5 -8.5,8.5h-15c-4.71221,0 -8.5,-3.78876 -8.5,-8.5v-15c0,-4.71239 3.78761,-8.5 8.5,-8.5zM34,12c-1.105,0 -2,0.895 -2,2c0,1.105 0.895,2 2,2c1.105,0 2,-0.895 2,-2c0,-1.105 -0.895,-2 -2,-2zM24,14c-5.50482,0 -10,4.49518 -10,10c0,5.50482 4.49518,10 10,10c5.50482,0 10,-4.49518 10,-10c0,-5.50482 -4.49518,-10 -10,-10zM24,17c3.88318,0 7,3.11682 7,7c0,3.88318 -3.11682,7 -7,7c-3.88318,0 -7,-3.11682 -7,-7c0,-3.88318 3.11682,-7 7,-7z"
                        ></path>
                      </g>
                    </g>
                  </svg>

                  <span>Instagram</span></a
                >
                <a
                  href="#"
                  class="-mx-3 sm:hidden flex items-center space-x-1 rounded-lg px-3 py-2.5 text-base font-semibold leading-7 hover:bg-gray-50 hover:text-black transition-colors"
                >
                  <svg
                    xmlns="http://www.w3.org/2000/svg"
                    x="0px"
                    y="0px"
                    width="100"
                    height="100"
                    viewBox="0,0,300,150"
                    class="w-6 h-6 inline"
                  >
                    <g
                      fill="#ffffff"
                      fill-rule="nonzero"
                      stroke="none"
                      stroke-width="1"
                      stroke-linecap="butt"
                      stroke-linejoin="miter"
                      stroke-miterlimit="10"
                      stroke-dasharray=""
                      stroke-dashoffset="0"
                      font-family="none"
                      font-weight="none"
                      font-size="none"
                      text-anchor="none"
                      style="mix-blend-mode: normal"
                    >
                      <g transform="scale(5.33333,5.33333)">
                        <path
                          d="M44.719,10.305c-0.295,-0.305 -0.749,-0.392 -1.136,-0.214l-0.164,0.075c-0.139,0.064 -0.278,0.128 -0.418,0.191c0.407,-0.649 0.73,-1.343 0.953,-2.061c0.124,-0.396 -0.011,-0.829 -0.339,-1.085c-0.328,-0.256 -0.78,-0.283 -1.135,-0.066c-1.141,0.693 -2.237,1.192 -3.37,1.54c-1.71,-1.659 -4.039,-2.685 -6.61,-2.685c-5.247,0 -9.5,4.253 -9.5,9.5c0,0.005 0,0.203 0,0.5l-0.999,-0.08c-9.723,-1.15 -12.491,-7.69 -12.606,-7.972c-0.186,-0.47 -0.596,-0.813 -1.091,-0.916c-0.494,-0.105 -1.007,0.05 -1.365,0.407c-0.198,0.199 -1.939,2.041 -1.939,5.561c0,2.508 1.118,4.542 2.565,6.124c-0.674,-0.411 -1.067,-0.744 -1.077,-0.753c-0.461,-0.402 -1.121,-0.486 -1.669,-0.208c-0.546,0.279 -0.868,0.862 -0.813,1.473c0.019,0.211 0.445,4.213 5.068,7.235l-0.843,0.153c-0.511,0.093 -0.938,0.444 -1.128,0.928c-0.189,0.485 -0.115,1.032 0.197,1.448c0.105,0.141 2.058,2.68 6.299,4.14c-2.265,0.755 -5.377,1.46 -9.099,1.46c-0.588,0 -1.123,0.344 -1.366,0.88c-0.244,0.536 -0.151,1.165 0.237,1.607c0.161,0.185 4.064,4.513 14.129,4.513c16.713,0 24.5,-15.515 24.5,-26v-0.5c0,-0.148 -0.016,-0.293 -0.022,-0.439c2.092,-2.022 2.879,-3.539 2.917,-3.614c0.189,-0.38 0.119,-0.838 -0.176,-1.142z"
                        ></path>
                      </g>
                    </g>
                  </svg>

                  <span>Twitter</span></a
                >
                <a
                  href="#"
                  class="-mx-3 flex items-center space-x-1 rounded-lg px-3 py-2.5 text-base font-semibold leading-7 hover:bg-gray-50 hover:text-black transition-colors"
                >
                  <UserCircleIcon class="h-6 w-6 inline" aria-hidden="true" />

                  <span>Account</span></a
                >
              </div>
            </div>
          </div>
        </DialogPanel>
      </Dialog>
    </header>
    <header
      v-else
      class="inset-x-0 top-0 z-50 fixed border-b bg-black/75 transition-opacity ease-out"
      v-motion-fade-visible
    >
      <nav
        class="flex items-center justify-between p-6 lg:px-8"
        aria-label="Global"
      >
        <div class="flex lg:flex-1">
          <a href="#" class="-m-1.5 p-1.5">
            <span class="sr-only">Your Company</span>
            <h1 class="h-8 uppercase font-bold">Huy</h1>
          </a>
        </div>
        <div class="flex lg:hidden">
          <button
            type="button"
            class="-m-2.5 inline-flex items-center justify-center rounded-md p-2.5"
            @click="mobileMenuOpen = true"
          >
            <span class="sr-only">Open main menu</span>
            <Bars3Icon class="h-6 w-6" aria-hidden="true" />
          </button>
        </div>
        <div class="hidden lg:flex lg:gap-x-12">
          <a
            v-for="item in navigation"
            :key="item.name"
            :href="item.href"
            class="text-sm font-semibold leading-6"
            >{{ item.name }}</a
          >
        </div>
        <div class="hidden lg:flex lg:flex-1 lg:justify-end">
          <a href="#" class="text-sm font-semibold leading-6">
            <UserCircleIcon class="h-6 w-6 inline" aria-hidden="true" />

            Account</a
          >
        </div>
      </nav>
      <Dialog
        class="lg:hidden"
        @close="mobileMenuOpen = false"
        :open="mobileMenuOpen"
      >
        <div class="fixed inset-0 z-50" />
        <DialogPanel
          class="fixed inset-y-0 end-0 z-50 w-full overflow-y-auto bg-black px-6 py-6 sm:max-w-sm sm:ring-1 sm:ring-gray-900/10"
        >
          <div class="flex items-center justify-between">
            <a href="#" class="-m-1.5 p-1.5">
              <span class="sr-only">Your Company</span>
              <h1 class="h-8">Huy</h1>
            </a>
            <button
              type="button"
              class="-m-2.5 rounded-md p-2.5"
              @click="mobileMenuOpen = false"
            >
              <span class="sr-only">Close menu</span>
              <XMarkIcon class="h-6 w-6" aria-hidden="true" />
            </button>
          </div>
          <div class="mt-6 flow-root">
            <div class="-my-6 divide-y divide-white">
              <div class="space-y-2 py-6">
                <a
                  v-for="item in navigation"
                  :key="item.name"
                  :href="item.href"
                  class="-mx-3 block rounded-lg px-3 py-2 text-base font-semibold leading-7 hover:bg-gray-50 hover:text-black transition-colors"
                  >{{ item.name }}</a
                >
              </div>
              <div class="py-6">
                <a
                  href="#"
                  class="flex sm:hidden items-center space-x-1 -mx-3 rounded-lg px-3 py-2.5 text-base font-semibold leading-7 hover:bg-gray-50 hover:text-black transition-colors"
                >
                  <svg
                    xmlns="http://www.w3.org/2000/svg"
                    x="0px"
                    y="0px"
                    width="100"
                    height="100"
                    viewBox="0,0,256,256"
                    class="w-6 h-6 inline"
                  >
                    <g
                      fill="#ffffff"
                      fill-rule="nonzero"
                      stroke="none"
                      stroke-width="1"
                      stroke-linecap="butt"
                      stroke-linejoin="miter"
                      stroke-miterlimit="10"
                      stroke-dasharray=""
                      stroke-dashoffset="0"
                      font-family="none"
                      font-weight="none"
                      font-size="none"
                      text-anchor="none"
                      style="mix-blend-mode: normal"
                    >
                      <g transform="scale(5.33333,5.33333)">
                        <path
                          d="M16.5,5c-6.33361,0 -11.5,5.16639 -11.5,11.5v15c0,6.33276 5.16621,11.5 11.5,11.5h15c6.33294,0 11.5,-5.16706 11.5,-11.5v-15c0,-6.33379 -5.16724,-11.5 -11.5,-11.5zM16.5,8h15c4.71124,0 8.5,3.78779 8.5,8.5v15c0,4.71106 -3.78894,8.5 -8.5,8.5h-15c-4.71221,0 -8.5,-3.78876 -8.5,-8.5v-15c0,-4.71239 3.78761,-8.5 8.5,-8.5zM34,12c-1.105,0 -2,0.895 -2,2c0,1.105 0.895,2 2,2c1.105,0 2,-0.895 2,-2c0,-1.105 -0.895,-2 -2,-2zM24,14c-5.50482,0 -10,4.49518 -10,10c0,5.50482 4.49518,10 10,10c5.50482,0 10,-4.49518 10,-10c0,-5.50482 -4.49518,-10 -10,-10zM24,17c3.88318,0 7,3.11682 7,7c0,3.88318 -3.11682,7 -7,7c-3.88318,0 -7,-3.11682 -7,-7c0,-3.88318 3.11682,-7 7,-7z"
                        ></path>
                      </g>
                    </g>
                  </svg>

                  <span>Instagram</span></a
                >
                <a
                  href="#"
                  class="-mx-3 sm:hidden flex items-center space-x-1 rounded-lg px-3 py-2.5 text-base font-semibold leading-7 hover:bg-gray-50 hover:text-black transition-colors"
                >
                  <svg
                    xmlns="http://www.w3.org/2000/svg"
                    x="0px"
                    y="0px"
                    width="100"
                    height="100"
                    viewBox="0,0,300,150"
                    class="w-6 h-6 inline"
                  >
                    <g
                      fill="#ffffff"
                      fill-rule="nonzero"
                      stroke="none"
                      stroke-width="1"
                      stroke-linecap="butt"
                      stroke-linejoin="miter"
                      stroke-miterlimit="10"
                      stroke-dasharray=""
                      stroke-dashoffset="0"
                      font-family="none"
                      font-weight="none"
                      font-size="none"
                      text-anchor="none"
                      style="mix-blend-mode: normal"
                    >
                      <g transform="scale(5.33333,5.33333)">
                        <path
                          d="M44.719,10.305c-0.295,-0.305 -0.749,-0.392 -1.136,-0.214l-0.164,0.075c-0.139,0.064 -0.278,0.128 -0.418,0.191c0.407,-0.649 0.73,-1.343 0.953,-2.061c0.124,-0.396 -0.011,-0.829 -0.339,-1.085c-0.328,-0.256 -0.78,-0.283 -1.135,-0.066c-1.141,0.693 -2.237,1.192 -3.37,1.54c-1.71,-1.659 -4.039,-2.685 -6.61,-2.685c-5.247,0 -9.5,4.253 -9.5,9.5c0,0.005 0,0.203 0,0.5l-0.999,-0.08c-9.723,-1.15 -12.491,-7.69 -12.606,-7.972c-0.186,-0.47 -0.596,-0.813 -1.091,-0.916c-0.494,-0.105 -1.007,0.05 -1.365,0.407c-0.198,0.199 -1.939,2.041 -1.939,5.561c0,2.508 1.118,4.542 2.565,6.124c-0.674,-0.411 -1.067,-0.744 -1.077,-0.753c-0.461,-0.402 -1.121,-0.486 -1.669,-0.208c-0.546,0.279 -0.868,0.862 -0.813,1.473c0.019,0.211 0.445,4.213 5.068,7.235l-0.843,0.153c-0.511,0.093 -0.938,0.444 -1.128,0.928c-0.189,0.485 -0.115,1.032 0.197,1.448c0.105,0.141 2.058,2.68 6.299,4.14c-2.265,0.755 -5.377,1.46 -9.099,1.46c-0.588,0 -1.123,0.344 -1.366,0.88c-0.244,0.536 -0.151,1.165 0.237,1.607c0.161,0.185 4.064,4.513 14.129,4.513c16.713,0 24.5,-15.515 24.5,-26v-0.5c0,-0.148 -0.016,-0.293 -0.022,-0.439c2.092,-2.022 2.879,-3.539 2.917,-3.614c0.189,-0.38 0.119,-0.838 -0.176,-1.142z"
                        ></path>
                      </g>
                    </g>
                  </svg>

                  <span>Twitter</span></a
                >
                <a
                  href="#"
                  class="-mx-3 flex items-center space-x-1 rounded-lg px-3 py-2.5 text-base font-semibold leading-7 hover:bg-gray-50 hover:text-black transition-colors"
                >
                  <UserCircleIcon class="h-6 w-6 inline" aria-hidden="true" />

                  <span>Account</span></a
                >
              </div>
            </div>
          </div>
        </DialogPanel>
      </Dialog>
    </header>
  </div>
</template>
