<template>
  <div class="item">
    <h1>{{ story.name }}</h1>
    <p>{{ story.text }}</p>
    <li @click="$emit('setActiveStory', index)">More Information</li>
  </div>
</template>

<script>
export default {
  name: "History",
  props: {
    story: {
      type: Object,
      default: () => ({})
    },
    index: {
      type: Number,
      default: 0
    }
  }
}
</script>

<style>

</style>