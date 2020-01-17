<template>
  <div id="app">
    <img src="/logo.png" style="height:100px" />
    <h1>Vue.js Event Behaviour</h1>
    <BasicEvents />
    <EventModifiers />
    <button @click="showManual = !showManual">Toggle Manual Component</button>
    <ManualEvents v-if="showManual" />
    <ChildEvents />
  </div>
</template>

<script>
import BasicEvents from './components/BasicEvents';
import EventModifiers from './components/EventMofiiers';
import ManualEvents from './components/ManualEvents';
import ChildEvents from './components/ChildEvents';

export default {
  name: 'app',
  components: {
    BasicEvents,
    EventModifiers,
    ManualEvents,
    ChildEvents
  },

  data: () => ({
    showManual: true
  })
};
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.section {
  border: 3px solid #41b883;
  padding: 1rem;
  margin-bottom: 1rem;
}
</style>
