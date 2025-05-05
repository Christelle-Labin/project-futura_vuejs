<script setup></script>

<template>
  <div class="h-line"></div>
  <footer>
    <p>Réalisé par <span>Labin Christelle</span> avec <span>Vue.js</span></p>
  </footer>
</template>

<style scoped>
.h-line {
  border: 1px solid var(--full-black);
  opacity: 0.2;
}
footer {
  width: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
  height: 60px;
  cursor: default;
}
#app > footer > p {
  font-weight: 700;
}
#app > footer > p > span {
  color: var(--font-purple);
}
</style>
