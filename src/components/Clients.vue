<template>
  <section class="clients" id="about">
    <img src="../assets/images/flag.png" alt="" class="flag">
    <div class="container">
      <div class="item">
        <div class="title">
          <h1>See why we are trusted the world over</h1>
          <p>
            The first rule of any technology used in a business is that automation applied to an efficient operation
            will magnify the efficiency.
          </p>
        </div>
         <div class="body">
           <Question
               v-for="question in questions"
               :key="question.id"
               :question="question"
           />
         </div>
      </div>
    </div>
  </section>
</template>

<script>
import Question from "@/components/Question";
import axios from "axios";

export default {
  name: "Clients",
  components: {
    Question
  },
  data() {
    return {
      is_open: false,
      api: 'https://alibaraka.pythonanywhere.com/api/questions/',
      questions: []
    }
  },
  methods: {
    async fetchQuestion() {
      const res = await axios.get(this.api)
      this.questions = await res.data
    }
  },
  mounted() {
    this.fetchQuestion()
  }
}
</script>

<style scoped>

</style>