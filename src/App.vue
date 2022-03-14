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
          class="transition ease-in-out delay-150 hover:-translate-y-1 hover:scale-110 border-2 border-transparent hover:border-2 hover:border-neutral-700 duration-300 flex-col flex space-y-6 rounded-lg shadow-6xl bg-[#202427] p-12"
        >
          <h1 class="text-neutral-100 font-bold text-xl">{{ repo.name }}</h1>
          <p class="text-neutral-100">{{ repo.description }}</p>
          <div class="flex space-x-4">
            <p
              class="text-neutral-100 font-bold text-center text-sm bg-[#0B0D0F] px-4 py-2 rounded-full"
            >
              <span class="mr-2">🗂</span>
              {{ repo.category }}
            </p>
            <p
              class="text-neutral-100 font-bold text-center bg-[#0B0D0F] px-4 py-2 rounded-full text-sm"
            >
              <span class="mr-2">✍️</span>
              @{{ repo.author }}
            </p>
          </div>
        </a>
      </div>
      <p class="text-neutral-100 mt-12 text-center">
        Build by
        <a
          class="text-transparent bg-clip-text bg-gradient-to-br from-green-400 to-green-600"
          href="https://github.com/maliksvd"
          >maliksvd.dev</a
        >
      </p>
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
