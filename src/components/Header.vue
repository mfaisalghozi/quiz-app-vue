<template>
  <nav>
    <ul>
      <li>Fancy Quiz App</li>
      <li>
        True Answer : <span class="correct">{{ numCorrect }}</span
        >/{{ numTotal }}
      </li>
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
  justify-content: center;
}

ul li {
  margin: 0 45px;
  font-weight: bold;
  font-size: 1.2em;
}

.correct {
  color: green;
}
</style>