<template>
  <div class="container">
     <Header @toggle-add-task="toggleAddTask" title="Task-a-lot" :showAddTask="showAddTask"/>
     <router-view :showAddTask="showAddTask"></router-view>
     <Footer />
  </div>
</template>

<script>
import Header from './components/Header'
import Footer from './components/Footer'

export default {
  name: 'App',
  components: {
   Header,
   Footer
  },
  data (){
    return {
      showAddTask: false
    }
  },
  methods: {
    toggleAddTask() {
      this.showAddTask = !this.showAddTask
    },
  },
}
</script>

<style>

@import url('https://fonts.googleapis.com/css2?family=Poppins:wght@300;400&display=swap');

* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body {
  font-family: 'Poppins', sans-serif;
  background-color: #fff;
  color: black;
}

.container {
  max-width: 500px;
  margin:180px auto;
  overflow: auto;
  min-height: 300px;
  border: 4px solid black;
  padding: 30px;
  border-radius: 5px;
  font-weight: 800;
}

header{
  color: cornflowerblue;
  text-decoration: underline;
  padding-left: 30px;
}

.btn {
  display: inline-block;
  background: #000;
  color: #fff;
  border: none;
  padding: 10px 20px;
  margin: 5px;
  border-radius: 5px;
  cursor: pointer;
  text-decoration: none;
  font-size: 15px;
  font-family: inherit;
}

.btn:focus {
  outline: none;
}

.btn:active {
  transform: scale(0.98);
}

.btn-block {
  display: block;
  width: 100%;
}
</style>
