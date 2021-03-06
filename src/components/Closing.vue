<template>
  <div class="closing">
    <h1>Thank You For Trying Our Quiz App ~</h1>
    <b-button @click="tryAgain" variant="primary">Try Again</b-button>
  </div>
</template>

<script>
export default {
  methods: {
    tryAgain() {
      location.reload();
    },
  },
};
</script>

<style>
.closing {
  display: flex;
  flex-direction: column;
  height: 100%;
  justify-content: center;
  align-items: center;
}
</style>