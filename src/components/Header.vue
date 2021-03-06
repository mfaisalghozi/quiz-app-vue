<template>
  <nav>
    <ul>
      <li>Fancy Quiz App</li>
      <li>Counter : {{ numCorrect }}/{{ numTotal }}</li>
    </ul>
  </nav>
</template>

<script>
export default {
  props: ["numCorrect", "numTotal"],
};
</script>

<style>
nav {
  border-bottom: 2px solid black;
}

ul {
  list-style-type: none;
  display: flex;
}

ul li {
  margin: 0 15px;
}
</style>