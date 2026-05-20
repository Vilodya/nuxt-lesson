<script setup>
const route = useRoute();
const { data: postData } = await useFetch(
  `http://localhost:3000/posts/${route.params.id}`,
);
</script>

<template>
  <div class="flex flex-col items-start w-1/2 gap-4 p-4 mx-auto">
    <div
      class="inline-block px-3 py-2 text-xs text-white uppercase border bg-sky-600 border-sky-700"
    >
      <NuxtLink :to="{ name: 'posts' }">Back</NuxtLink>
    </div>
    <div class="w-full p-4 bg-white border border-gray-200">
      <h3 class="text-lg text-gray-700">
        {{ postData.title }}
      </h3>
      <p class="mt-2 text-xs text-gray-500">{{ postData.content }}</p>
    </div>
  </div>
</template>
