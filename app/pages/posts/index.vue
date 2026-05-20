<script setup>
definePageMeta({
  layout: "main",
});

const { data: postData } = await useFetch("http://localhost:3000/posts");
</script>

<template>
  <div class="flex flex-col items-center w-1/2 gap-4 p-4 mx-auto">
    <div
      v-for="post in postData"
      :key="post.id"
      class="w-full p-4 bg-white border border-gray-200"
    >
      <h3 class="text-lg text-gray-700">
        <NuxtLink :to="{ name: 'posts-id', params: { id: post.id } }">
          {{ post.title }}
        </NuxtLink>
      </h3>
      <p class="mt-2 text-xs text-gray-500">{{ post.content }}</p>
    </div>
  </div>
</template>
