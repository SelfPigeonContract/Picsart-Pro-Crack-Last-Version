<template>
  <div>
    <input v-model="inputData" placeholder="Enter data to process" />
    <button @click="processData">Process</button>
    <ul>
      <li v-for="(item, index) in processedData" :key="index">{{ item }}</li>
    </ul>
  </div>
</template>
<script>
export default {
  data() {
    return {
      inputData: '',
      processedData: []
    };
  },
  methods: {
    processData() {
      const dataArray = this.inputData.split(',').map(item => item.trim()).filter(item => item);
      this.processedData = dataArray.map(item => item.toUpperCase()).sort();
    }
  }
};
</script>
<style scoped>
div {
  margin: 20px;
}
input {
  padding: 10px;
  margin-right: 10px;
}
button {
  padding: 10px;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  margin: 5px 0;
}
</style>
