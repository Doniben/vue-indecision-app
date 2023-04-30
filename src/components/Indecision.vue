<template>
  <img v-if="img" alt="Vue logo" :src="img" />
  <div class="indecision-container">
    <MagoSectionVue :anwser="answer" />
    <input type="text" placeholder="Hazme una pregunta" v-model="question" />
    <p>Recuerda terminar con un signo de interrogación (?)</p>
    <div v-if="isValidQuestion">
      <h1>{{ question }}</h1>
      <h2>{{ answer }}</h2>
    </div>
  </div>
</template>

<script>
import './mago.css'
import MagoSectionVue from './MagoSection.vue';
export default {
  components: {
    MagoSectionVue
  },
  data() {
    return {
      question: null,
      answer: null,
      img: null,
      isValidQuestion: false,
    };
  },
  methods: {
    async getAnswer() {
      this.answer = "Pensando...";
      const { image, answer } = await fetch("https://yesno.wtf/api").then((r) =>
        r.json()
      );
      this.answer = answer === "yes" ? "Sí!" : "No!";
      this.img = image;
    },
  },
  watch: {
    question(newValue) {
      this.isValidQuestion = false;
      if (!newValue.includes("?")) return;
      this.isValidQuestion = true;
      this.getAnswer();
    },
  },
};
</script>

<style scoped>
img,
.bg-dark {
  height: 100vh;
  left: 0px;
  max-height: 100%;
  max-width: 100%;
  position: fixed;
  top: 0px;
  width: 100vw;
}

.indecision-container {
  position: relative;
  z-index: 99;
}

input {
  width: 250px;
  padding: 10px 15px;
  border-radius: 5px;
  border: none;
  z-index: 1000;
}
input:focus {
  outline: none;
}

p {
  color: white;
  font-size: 20px;
  margin-top: 0px;
}

h1,
h2 {
  color: white;
}

h2 {
  margin-top: 150px;
}

</style>