<template>
  <section class="success" id="blog">
    <div class="container">
      <div class="wrapper">
        <div class="left">
          <h1>How our client made 10x revenue</h1>
          <img
              :src="stories[active_story].image ? stories[active_story].image : default_image"
              :alt="stories[active_story].name">
          <div class="made">
            <div class="learned">
              <h1>{{ stories[active_story].name }}</h1>
              <p>{{ stories[active_story].text }}</p>
            </div>
            <button class="btn">more stories</button>
          </div>
        </div>
        <div class="right">
          <h1 class="title">Other successful stories</h1>
          <History
              v-for="(story, idx) in stories"
              :key="story.id"
              :story="story"
              @setActiveStory="setActiveHistory"
              :index="idx"
          />
        </div>
      </div>
    </div>
  </section>
</template>

<script>
import History from "@/components/History";
import axios from "axios";

export default {
  name: "Success",
  components: {
    History
  },
  data() {
    return {
      api: 'https://alibaraka.pythonanywhere.com/api/stories/',
      stories: [{}],
      active_story: 0,
      default_image: 'https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRU2kVc1rpu0zFLcinUxktDvMW7xSnsFwo4jA&usqp=CAU'
    }
  },
  methods: {
    async fetchStory() {
      const response = await axios.get(this.api)
      this.stories = await response.data
    },
    setActiveHistory(index) {
      this.active_story = index
    }
  },
  mounted() {
    this.fetchStory()
  }
}
</script>

<style scoped>

</style>