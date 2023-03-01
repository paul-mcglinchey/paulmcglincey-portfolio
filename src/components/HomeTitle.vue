<template>
  <h1 class="group text-6xl font-bold tracking-wider font-mono text-green-500 p-4">
    <a href="mailto:paulmcglinchey789@gmail.com" class="relative before:w-1 before:max-h-full before:py-8 before:bg-green-500 before:block before:absolute before:bottom-0 animated-caret">
      <span>paul mcglinchey</span>
    </a>
  </h1>
</template>

<style scoped>

a.animated-caret::before {
  animation: flicker 0.9s linear infinite reverse both;
  animation: typing 2s linear both;
}

@keyframes flicker {
  0% {
    opacity: 0%;
  }

  20%, 100% {
    opacity: 70%;
  }
}

@keyframes typing {
  0% {
    left: 0%;
  }

  10% {
    left: 4%;
  }

  20% {
    left: 30%
  }

  100% {
    left: 100%;
  }
}

</style>