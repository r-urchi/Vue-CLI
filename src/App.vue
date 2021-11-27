<template>
  <div id="app">
    <h1>Desafío - Clase 6</h1>
    <Counter msg="Contador"/>
    <Table msg="Tabla"/>
  </div>
</template>

<script>
import Counter from './components/Counter.vue'
import Table from './components/Table.vue'

export default {
  name: 'App',
  components: {
    Counter,
    Table,
  },
}
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  background: #FBF3E4;
  font-family: sans-serif;
  color: #105652;
}

#app {
  width: 100%;
  height: 100%;
  display: flex;
  justify-content: center;
  flex-direction: column;
  align-items: center;
}

.container{
  width: 100%;
  height: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
}

h2 {
  text-align: center;
  text-transform: uppercase;
  font-size: 2.5rem;
  margin: 3rem auto 2rem auto;
}
</style>
