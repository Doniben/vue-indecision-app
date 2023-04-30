<template>
    <indecision />
    <p class="signature">Made by @Doniben</p>
</template>

<script>

import Indecision from './components/Indecision.vue'

export default {
  name: 'App',
  components: {
    Indecision,
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 30px;
}

body {
  height: 100vh;
  background: linear-gradient(-45deg, #2ecbaa, #6e1e62, #21b6b6, #de4126);
  background-size: 400% 400%;
  -webkit-animation: Gradient 15s ease infinite;
  -moz-animation: Gradient 15s ease infinite;
  animation: Gradient 15s ease infinite;
}

@-webkit-keyframes Gradient {
  0% { background-position: 0% 50%; }
  50% { background-position: 100% 50%; }
  100% { background-position: 0% 50%; }
}

@-moz-keyframes Gradient {
  0% { background-position: 0% 50%; }
  50% { background-position: 100% 50%; }
  100% { background-position: 0% 50%; }
}

@keyframes Gradient {
  0% { background-position: 0% 50%; }
  50% { background-position: 100% 50%; }
  100% { background-position: 0% 50%; }
}

.signature {
    color: white;
    position: absolute;
    bottom: 1rem;
    left: 1rem;
}
</style>

