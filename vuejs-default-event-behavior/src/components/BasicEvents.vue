<template>
  <div class="section">
    <h1>Event Basics</h1>
    <h2>Single handler</h2>
    <button v-on:click="counter += 1">Add 1</button>
    <p>The button above has been clicked {{ counter }} times.</p>
    <button @click="counter += 1">Add 1</button>
    <p>The button above has been clicked {{ counter }} times.</p>

    <h2>Multiple handlers</h2>
    <!-- <button @click="counter += 1" @click="alert(counter)">
      Do multiple things
    </button> -->
    <button @click="onClick">Do multiple things</button>
  </div>
</template>

<script>
export default {
  data: () => ({
    counter: 0
  }),

  methods: {
    onClick() {
      this.counter += 1;
      alert(this.counter);
    }
  }
};
</script>
