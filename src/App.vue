<script setup>
import { ArrowDownIcon } from "@heroicons/vue/24/outline";
import Header from "./components/Header.vue";
import Body from "./components/Body.vue";
import Footer from "./components/Footer.vue";
import { MotionGroupComponent } from "@vueuse/motion";
</script>

<template>
  <Header />
  <!-- Hero Section -->
  <section class="h-screen hero-img relative">
    <div
      class="grid grid-cols-4 grid-flow-row gap-4 absolute top-[50%] -translate-y-1/2 px-8"
    >
      <div class="col-span-1">
        <MotionGroupComponent
          class="hidden sm:flex relative end-8 lg:end-28 top-32 lg:top-0 items-center rotate-90 space-x-2 place-content-center lg:place-content-end"
          preset="slideVisibleOnceLeft"
          :duration="700"
          is="div"
        >
          <p class="">Follow us</p>
          <svg
            xmlns="http://www.w3.org/2000/svg"
            x="0px"
            y="0px"
            width="100"
            height="100"
            viewBox="0,0,256,256"
            class="w-6 h-6 -rotate-90"
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
          <svg
            xmlns="http://www.w3.org/2000/svg"
            x="0px"
            y="0px"
            width="100"
            height="100"
            viewBox="0,0,300,150"
            class="w-6 h-6 -rotate-90"
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
        </MotionGroupComponent>
      </div>

      <MotionGroupComponent
        class="w-full col-span-2 flex flex-col space-y-10"
        preset="slideVisibleOnceLeft"
        :duration="700"
        is="div"
      >
        <div class="inline-flex items-center space-x-2 w-full">
          <div
            class="w-[10%] h-[0.1rem] border-t-2 border-primary leading-[80%]"
          ></div>
          <h5 class="uppercase text-primary text-lg">A hiking guide</h5>
        </div>
        <h1 class="capitalize text-6xl text-pretty">
          Be prepared for the Mountains and beyond!
        </h1>
        <p>
          scroll down <ArrowDownIcon class="w-6 h-6 inline animate-bounce" />
        </p>
      </MotionGroupComponent>

      <div class="col-span-1"></div>
    </div>
  </section>
  <Body />
  <Footer />
</template>

<style scoped></style>
