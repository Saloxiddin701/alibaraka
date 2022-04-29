<template>
  <div class="wrap">
    <div class="wrapper">
      <div class="head">
        <h1>{{ question.question }}</h1>
        <i @click="is_open = !is_open" class="fa fa-plus"></i>
      </div>
        <p v-if="is_open">{{ question.answer }}</p>
    </div>
  </div>
</template>

<script>
export default {
  name: "Question",
  props: {
    question: {
      type: Object,
      default: () => ({})
    }
  },
  data() {
    return {
      is_open: false
    }
  }
}
</script>

<style scoped>

</style>