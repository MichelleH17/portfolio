<template>
  <div class="flex items-center space-x-2">
    <div v-if="showNextModeLabel" class="text-xs">Change to {{ nextMode }}</div>
    <button @click="toggleMode" @mouseenter="showNextModeLabel = true" @mouseleave="showNextModeLabel = false" class="hover:bg-green-100 dark:hover:bg-green-300 px-2 py-1 text-gray-500">{{ nextModeIcon }}</button>
  </div>
</template>

<script lang="ts" setup>
const showNextModeLabel = ref(false)
const colorMode = useColorMode()

const modes = ["system", "light", "dark"]

const nextModeIcons = {
  system: '🌓',
  light: '🌕',
  dark: '🌑'
}

const nextMode = computed(() => {
  const currentModeIndex = modes.indexOf(colorMode.preference)
  let nextModeIndex = null

  if (currentModeIndex + 1 === modes.length) {
    nextModeIndex = 0
  } else {
  nextModeIndex = currentModeIndex + 1
  }

  return modes[nextModeIndex]
})

const nextModeIcon = computed(() => nextModeIcons[nextMode.value])

const toggleMode = () => colorMode.preference = nextMode.value
</script>

<style>

</style>