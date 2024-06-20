<template>
  <div id="app" :style="{ backgroundColor: backgroundColor }">
    <h1 :style="{ color: textColor }">Nested Components with Emit and Slot</h1>
    <parent-component />
    <button @click="changeColor">Change Color</button>
  </div>
</template>

<script>
import ParentComponent from './components/ParentComponent.vue';

export default {
  name: 'App',
  components: {
    ParentComponent
  },
  data() {
    return {
      textColor: '#2c3e50',
      backgroundColor: '#ffffff'
    };
  },
  methods: {
    changeColor() {
      const colors = ['#2c3e50', '#ff0000', '#00ff00', '#0000ff', '#ffa500', '#ffffff', '#f0f8ff', '#faebd7'];
      this.textColor = colors[Math.floor(Math.random() * colors.length)];
      this.backgroundColor = colors[Math.floor(Math.random() * colors.length)];
    }
  }
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  padding: 20px; /* Add some padding to the container */
  transition: background-color 0.5s ease; /* Smooth transition for background color change */
}

h1 {
  color: #2c3e50;
}

button {
  padding: 10px 20px;
  background-color: #4CAF50;
  color: white;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  font-size: 16px;
  margin-top: 20px;
}

button:hover {
  background-color: #45a049;
}

button:active {
  background-color: #3e8e41;
}
</style>
