<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <AppTable />
    <AppTable :appData="appData" @clickRow="showId" />
  </div>
</template>

<script>
//import HelloWorld from './components/HelloWorld.vue'
import AppTable from './components/AppTable.vue'

export default {
  name: 'App',
  components: {
  //  HelloWorld,
    AppTable,
  },
  data() {
    return {
      appData: [
        {
          id: 1,
          name: 'Jhon',
          lastName: 'Smith',
          age: 21
        },
        {
          id: 2,
          name: 'Jhon 2',
          lastName: 'Smith 2',
          age: 22
        }
      ]
    }
  }, 
  methods: {
    showId(id) {
      alert(id)
    }
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
  margin-top: 60px;
}
</style>
