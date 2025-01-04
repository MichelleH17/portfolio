<template>
  <nav class="font-mono">
    <ul class="flex space-x-6">
      <li>
        <NuxtLink to="/" class="link">Main</NuxtLink>
      </li>
      <li>
        <NuxtLink to="/about" class="link">About</NuxtLink>
      </li>
      <li>
        <NuxtLink to="/projects" class="link">Projects</NuxtLink>
      </li>
    </ul>
  </nav>
</template>

<script lang="ts" setup>

</script>

<style lang="postcss" scoped>
.link {
  @apply p-1 hover:bg-green-100
}
</style>