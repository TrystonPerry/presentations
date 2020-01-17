// Learn about event modifiers:
https://vuejs.org/v2/guide/events.html#Event-Modifiers
<template>
  <div class="section">
    <h1>Event Modifiers</h1>
    <button @click="onClick">Normal <span>Click</span></button>
    <button @click.self="onClick">Only Self <span>Click</span></button>
    <form @submit="onSubmit">
      <h2>Normal Form</h2>
      <input type="text" name="name" placeholder="Enter your name!" />
      <button type="submit">Submit</button>
    </form>
    <form @submit.prevent="onSubmit">
      <h2>Prevented Form</h2>
      <input type="text" name="name" placeholder="Enter your name!" />
      <button type="submit">Submit</button>
    </form>
  </div>
</template>

<script>
export default {
  methods: {
    onClick(event) {
      console.log(event.target);
    },

    onSubmit() {
      alert('Submitted!');
    }
  }
};
</script>
