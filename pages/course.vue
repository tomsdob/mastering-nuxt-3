<script lang="ts" setup>
import { useCourse } from '~/composables/useCourse';

const { chapters } = useCourse();
</script>

<template>
  <div class="p-12 bg-gray-100 w-full h-full min-h-screen flex flex-col items-center">
    <div class="prose mb-12">
      <h1>
        <span class="font-medium">
          Course:
          <span class="font-bold">Mastering Nuxt 3</span>
        </span>
      </h1>
    </div>
    <div class="flex flex-row justify-center flex-grow">
      <div class="prose mr-4 p-8 bg-white rounded-md min-w-[20ch] max-w-[30ch] flex flex-col">
        <h3>Chapters</h3>
        <div v-for="chapter in chapters" :key="chapter.slug" class="space-y-1 mb-4 flex flex-col">
          <h4>{{ chapter.title }}</h4>
          <NuxtLink
            v-for="(lesson, index) in chapter.lessons"
            :key="lesson.slug"
            class="flex space-x-1 no-underline prose-sm py-1 font-normal hover:text-green-600 transition-all duration-200"
            :to="`/course/chapter/${chapter.slug}/lesson/${lesson.slug}`"
          >
            <span>{{ index + 1 }}.</span>
            <span>{{ lesson.title }}</span>
          </NuxtLink>
        </div>
      </div>
      <div class="prose p-12 bg-white rounded-md w-[65ch]">
        <NuxtPage />
      </div>
    </div>
  </div>
</template>
