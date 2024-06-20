<template>
  <div class="container">
    <header class="header">
      <h1>Header Section</h1>
    </header>

    <main class="grandchild-container">
      <h4>Grandchild Component</h4>
      <button @click="emitData">Send Data to Parent</button>
    </main>

    <footer class="footer">
      <p>Footer Section</p>
    </footer>
  </div>
</template>

<script>
export default {
  name: 'GrandchildComponent',
  methods: {
    emitData() {
      this.$emit('grandchildEvent', 'Data from Grandchild Component');
    }
  }
};
</script>

<style scoped>
.container {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.header, .footer {
  width: 100%;
  padding: 10px;
  background-color: #f1f1f1;
  text-align: center;
}

.header h1, .footer p {
  margin: 0;
}

.grandchild-container {
  padding: 10px;
  border: 1px solid #bbb;
  border-radius: 10px;
  margin: 20px;
  background-color: #ddf;
}

h4 {
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
}

button:hover {
  background-color: #45a049;
}

button:active {
  background-color: #3e8e41;
}
</style>
