<template>
  <section class="max-w-6xl mx-auto py-12">
    <Sidebar />
    <div class="lg:pl-44">
      <div class="grid grid-cols-1 md:grid-cols-2 gap-10 px-12 md:px-0">
        <a
          v-for="repo in repos"
          :key="repo.id"
          :href="repo.link"
          target="_blank"
          class="transition ease-in-out delay-150 hover:-translate-y-1 hover:scale-110 hover:bg-green-100 border-2 border-transparent hover:border-2 hover:border-green-200 duration-300 flex-col flex space-y-6 rounded-lg shadow bg-white p-12"
        >
          <h1 class="text-[#161616] font-bold text-xl">{{ repo.name }}</h1>
          <p class="text-[#161616]">{{ repo.description }}</p>
          <div class="flex space-x-4">
            <p
              class="text-pink-800 font-bold text-center text-sm bg-pink-100 border-2 border-pink-200 px-4 py-2 rounded-full"
            >
              <span class="mr-2">🗂</span>
              {{ repo.category }}
            </p>
            <p
              class="text-indigo-800 font-bold text-center bg-indigo-100 border-2 border-indigo-200 px-4 py-2 rounded-full text-sm"
            >
              <span class="mr-2">✍️</span>
              @{{ repo.author }}
            </p>
          </div>
        </a>
      </div>
    </div>
  </section>
</template>

<script>
import Sidebar from './components/Sidebar.vue';

import reposData from './api/repos.json';

export default {
  components: { Sidebar },
  data() {
    return {
      repos: reposData,
    };
  },
};
</script>
