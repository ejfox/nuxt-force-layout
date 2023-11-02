<template>
  <div>
    Nuxt module playground!
    <ForceLayout :edges="edges" :nodes="nodes" />
  </div>
</template>

<script setup>
const { data: nodes } = await useAsyncData('nodes', () => fetch('/api/nodes').then(res => res.json()))

const { data: edges } = await useAsyncData('edges', () => fetch('/api/edges').then(res => res.json()))
</script>
