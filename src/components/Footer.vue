<script setup>
const BlogInfo = [
  {
    name: "About HUY",
    href: "#",
  },
  {
    name: "Contributors & Writers",
    href: "#",
  },
  {
    name: "Write For Us",
    href: "#",
  },
  {
    name: "Contact Us",
    href: "#",
  },
  {
    name: "Privacy Policy",
    href: "#",
  },
];

const CompanyInfo = [
  {
    name: "The Team",
    href: "#",
  },
  {
    name: "Jobs",
    href: "#",
  },
  {
    name: "Press",
    href: "#",
  },
];
</script>
<template>
  <section class="flex flex-col divide-y divide-white sm:px-8 py-8">
    <div
      class="grid gap-8 auto-cols-auto md:grid-cols-2 grid-flow-row place-content-center divide-y divide-white md:divide-y-0 place-items-center sm:px-8 py-8 flex-wrap"
    >
      <div class="col-span-1 md:place-self-start flex flex-col space-y-6">
        <h1 class="uppercase font-bold">Huy</h1>
        <p class="text-sm">
          Get out there & discover your next slope, mountain & destination!
        </p>
      </div>
      <div
        class="col-span-1 w-full md:w-auto pt-4 md:pt-0 md:place-self-end flex space-x-16 md:space-x-32"
      >
        <div class="flex flex-col space-y-4">
          <h3 class="text-primary">More on The Blog</h3>
          <div
            v-for="(blog, index) in BlogInfo"
            class="flex flex-col space-y-4"
            :key="index"
          >
            <a :href="blog.href">{{ blog.name }}</a>
          </div>
        </div>
        <div class="flex flex-col space-y-4">
          <h3 class="text-primary">More on HUY</h3>
          <div
            v-for="(item, index) in CompanyInfo"
            class="flex flex-col space-y-4"
            :key="index"
          >
            <a :href="item.href">{{ item.name }}</a>
          </div>
        </div>
      </div>
    </div>
    <p class="pt-2 text-xs text-white/75">
      Copyright 2023 MNTN, Inc. Terms & Privacy
    </p>
  </section>
</template>
