<script setup></script>

<template>
  <header>
    <h1>FUTURA</h1>
    <nav>
      <ul>
        <li>SCIENCES<font-awesome-icon :icon="['fas', 'angle-down']" /></li>
        <li>SANTE<font-awesome-icon :icon="['fas', 'angle-down']" /></li>
        <li>TECH<font-awesome-icon :icon="['fas', 'angle-down']" /></li>
        <li>MAISON<font-awesome-icon :icon="['fas', 'angle-down']" /></li>
        <li>PLANETE<font-awesome-icon :icon="['fas', 'angle-down']" /></li>
      </ul>
    </nav>
    <button>JE M'ABONNE</button>
  </header>
</template>

<style scoped>
#app > header {
  height: 30px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 20px 50px;
  background: var(--linear-gradient-purple);
  color: var(--full-white);
}
h1 {
  font-weight: 700;
  font-size: 1.5rem;
  cursor: default;
}
ul {
  display: flex;
  gap: 30px;
  cursor: pointer;
}
li {
  display: flex;
  gap: 10px;
}
button {
  padding: 8px 15px;
  color: var(--full-white);
  background: var(--bckg-clr-button);
  border: none;
  box-shadow: 3px 3px 1px 0px rgb(27, 26, 26);
  cursor: pointer;
}

/* --- MEDIA QUERIES --- */
@media (max-width: 992px) {
  #app > header {
    padding: 15px 30px;
  }
  ul {
    gap: 15px;
  }
  li {
    font-size: 0.9rem;
  }
  button {
    padding: 6px 12px;
    font-size: 0.9rem;
  }
}
@media (max-width: 860px) {
  nav ul {
    display: none;
  }
  header {
    flex-direction: column;
    gap: 10px;
    padding: 20px;
  }
  h1 {
    font-size: 1.2rem;
  }
  button {
    padding: 5px 10px;
  }
}

@media (max-width: 576px) {
  h1 {
    font-size: 1rem;
  }
  button {
    font-size: 0.8rem;
  }
}
</style>
