<template>
  <div class="section">
    <h1>Child Events</h1>
    <div class="container">
      <h2></h2>
      <div @mouseover="onMouseover" @mouseout="onMouseout" class="box">
        <div v-if="showChild">Mouseover</div>
      </div>

      <div @mouseenter="onMouseenter" @mouseleave="onMouseleave" class="box">
        <div v-if="showChild">Mouseenter</div>
      </div>

      <div id="mouse-over" class="box">
        <div v-if="showChild">Custom Mouseover</div>
      </div>

      <div id="mouse-enter" class="box">
        <div v-if="showChild">Custom Mouseenter</div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data: () => ({
    showChild: false
  }),

  methods: {
    onMouseover(event) {
      console.log('@mouseover');
      this.showChild = true;
    },

    onMouseout(event) {
      console.log('@mouseout');
      this.showChild = false;
    },

    onMouseenter(event) {
      console.log('@mouseenter');
      this.showChild = true;
    },

    onMouseleave(event) {
      console.log('@mouseleave');
      this.showChild = false;
    }
  },

  mounted() {
    const mouseover = document.getElementById('mouse-over');
    mouseover.addEventListener('mouseover', this.onMouseover);
    mouseover.addEventListener('mouseout', this.onMouseout);
    const mouseenter = document.getElementById('mouse-enter');
    mouseenter.addEventListener('mouseenter', this.onMouseenter);
    mouseenter.addEventListener('mouseleave', this.onMouseleave);
  },

  beforeDestroy() {
    const mouseover = document.getElementById('mouse-over');
    mouseover.removeEventListener('mouseover', this.onMouseover);
    mouseover.removeEventListener('mouseout', this.onMouseout);
    const mouseenter = document.getElementById('mouse-enter');
    mouseenter.removeEventListener('mouseenter', this.onMouseenter);
    mouseenter.removeEventListener('mouseleave', this.onMouseleave);
  }
};
</script>

<style>
.container {
  display: flex;
}
.box {
  height: 5rem;
  width: 10rem;
  background: #41b883;
  display: flex;
  color: white;
  align-items: center;
  justify-content: center;
  font-weight: bold;
  margin: 0.25rem;
}
</style>
