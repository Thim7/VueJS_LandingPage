<script setup>
import { ArrowRightIcon } from "@heroicons/vue/24/outline";
import { MotionComponent, MotionGroupComponent } from "@vueuse/motion";
import { defineProps } from "vue";
const props = defineProps({
  intro: Array,
});

function getImageURL(img) {
  return new URL(`../assets/img/${img}`, import.meta.url).href;
}
</script>
<template>
  <div v-for="(item, index) in intro" :key="index">
    <div
      v-if="item.isReversed"
      class="grid grid-cols-2 grid-flow-row gap-8 lg:gap-32 mb-48"
    >
      <div class="md:col-span-1">
        <MotionComponent
          preset="slideVisibleOnceLeft"
          :duration="700"
          is="img"
          :src="getImageURL(item.img)"
          alt="Illustrate image"
          class="w-full h-auto max-h-[520px] object-cover rounded hidden md:block"
          loading="lazy"
        />
      </div>
      <MotionGroupComponent
        class="intro-container relative w-full flex flex-col items-start space-y-8 col-span-2 md:col-span-1 shrink-0"
        preset="slideVisibleOnceRight"
        :duration="700"
        is="div"
      >
        <div class="absolute top-[-32px] start-[-64px] -z-0">
          <h1 class="text-9xl opacity-30">0{{ index + 1 }}</h1>
        </div>
        <div class="inline-flex items-center space-x-2 w-full">
          <div
            class="w-[10%] h-[0.1rem] border-t-2 border-primary leading-[80%]"
          ></div>
          <h5 class="uppercase text-primary">{{ item.subTitle }}</h5>
        </div>
        <h1 class="capitalize text-4xl text-pretty">
          {{ item.title }}
        </h1>
        <p class="text-sm text-pretty">
          {{ item.description }}
        </p>
        <button class="text-primary">
          Read more <ArrowRightIcon class="w-6 h-6 inline" />
        </button>
      </MotionGroupComponent>
    </div>
    <div v-else class="grid grid-cols-2 grid-flow-row gap-8 lg:gap-32 mb-48">
      <MotionGroupComponent
        class="relative w-full flex flex-col items-start space-y-8 col-span-2 md:col-span-1"
        preset="slideVisibleOnceLeft"
        :duration="700"
        is="div"
      >
        <div class="absolute top-[-32px] start-[-64px] -z-0">
          <h1 class="text-9xl opacity-30">0{{ index + 1 }}</h1>
        </div>
        <div class="inline-flex items-center space-x-2 w-full">
          <div
            class="w-[10%] h-[0.1rem] border-t-2 border-primary leading-[80%]"
          ></div>
          <h5 class="uppercase text-primary">{{ item.subTitle }}</h5>
        </div>
        <h1 class="capitalize text-4xl text-pretty">
          {{ item.title }}
        </h1>
        <p class="text-sm text-pretty">
          {{ item.description }}
        </p>
        <button class="text-primary">
          Read more <ArrowRightIcon class="w-6 h-6 inline" />
        </button>
      </MotionGroupComponent>
      <div class="md:col-span-1">
        <MotionComponent
          preset="slideVisibleOnceRight"
          :duration="700"
          is="img"
          :src="getImageURL(item.img)"
          alt="Illustrate image"
          class="w-full h-auto max-h-[520px] object-cover rounded hidden md:block"
          loading="lazy"
        />
      </div>
    </div>
  </div>
</template>
