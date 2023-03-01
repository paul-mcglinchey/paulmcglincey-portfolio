<script setup lang="ts">
import { RouterView } from 'vue-router'
import HomeTitle from './components/HomeTitle.vue'
import './index.css';
import GithubWhiteIcon from './assets/icons/GithubWhiteIcon.vue'
import { onMounted, ref } from 'vue';

const githubUserData = ref()

const getGitHubUserData = async () => {
  var res = await fetch('https://api.github.com/users/paul-mcglinchey', {
    method: 'GET'
  })

  var json = await res.json()

  githubUserData.value = json
}

onMounted(() => {
  getGitHubUserData()
})

</script>

<template>
  <header>
    <div class="flex justify-between">
      <HomeTitle />
      <div class="flex p-4">
        <div class="relative group flex flex-grow">
          <div class="flex flex-grow items-center justify-between relative z-20 p-5">
            <a :href="githubUserData?.html_url" class="inline-flex items-center tracking-wide font-semibold text-gray-200 text-lg invisible opacity-0 group-hover:visible group-hover:opacity-100 transition-all hover:text-blue-300">
              {{ githubUserData?.login }}
              <GithubWhiteIcon class="w-5 h-5 ml-2" />
            </a>
            <img :src="githubUserData?.avatar_url" class="w-12 h-12 rounded-full outline outline-2 outline-green-500 outline-offset-2" />
          </div>
          <div
            class="w-full h-40 bg-slate-800 rounded-lg absolute z-10 right-0 top-0 opacity-0 invisible group-hover:visible group-hover:opacity-100 transition-all">
          </div>
        </div>
      </div>
    </div>
  </header>
  <div>
  </div>
</template>
