<template>
  <div class="section">
    <h1>Manual Events</h1>
    <button @click="onClick">Auto Listener</button>
    <button id="my-btn">Manual Listener</button>
  </div>
</template>

<script>
export default {
  methods: {
    onClick() {
      console.log('Clicked!');
    },

    onResize() {
      console.log('Resized!');
    }
  },

  mounted() {
    document.getElementById('my-btn').addEventListener('click', this.onClick);
    window.addEventListener('resize', this.onResize);
  },

  beforeDestroy() {
    window.removeEventListener('resize', this.onResize);
  }
};
</script>

<style></style>
