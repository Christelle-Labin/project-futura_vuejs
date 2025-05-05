<script setup>
import articlesFutura from '../assets/data/articles.json'
</script>

<template>
  <section class="wrapper">
    <img :src="articlesFutura.frontPage.image" :alt="articlesFutura.frontPage.title" />
    <div class="container">
      <div class="v-line">
        <h3>
          <span class="gradient-text">{{ articlesFutura.frontPage.category.toUpperCase() }}</span>
          {{ articlesFutura.frontPage.subCategory.toUpperCase() }}
        </h3>
        <h2>{{ articlesFutura.frontPage.title }}</h2>
      </div>
      <div class="content">
        <p>{{ articlesFutura.frontPage.teaser }}</p>
      </div>
    </div>
  </section>
</template>

<style scoped>
.wrapper {
  width: 100%;
  height: 550px;
  display: flex;
  justify-content: center;
  align-items: center;
  overflow: hidden;
  background-color: var(--bckg-main);
}

section > img {
  max-height: 100%;
  width: 100%;
  padding-top: 100px;
  object-fit: cover;
  object-position: bottom;
}
.container {
  position: absolute;
  top: 250px;
  left: 180px;
  min-width: 300px;
  max-width: 650px;
}
.v-line {
  display: flex;
  flex-wrap: wrap;
}
.v-line ::before {
  content: '';
  position: absolute;
  top: 0px;
  width: 5px;
  height: 7rem;
  left: -5px;
  background: var(--linear-gradient-purple);
  z-index: 0;
  transition: transform 150ms ease-in-out;
  will-change: transform;
}
.gradient-text {
  background: var(--linear-gradient-purple);
  background-clip: text;
  -webkit-text-fill-color: transparent;
  font-weight: 600;
}
h3 {
  display: flex;
  gap: 10px;
  font-size: small;
  margin-left: 0.75rem;
  background-color: var(--full-black);
  padding: 5px 5px 8px;
  width: fit-content;
  margin: 0px;
  color: var(--full-white);
  cursor: default;
}
h3 > span {
  font-size: small;
}
h2 {
  background-color: var(--full-black);
  font-family: Merriweather, serif;
  font-size: 26px;
  padding: 5px 5px 8px;
  margin: 0;
  color: var(--full-white);
  line-height: 1.4;
  word-break: break-word; /* mots très longs */
  cursor: pointer;
}

p {
  margin-top: 20px;
  background-color: var(--full-black);
  font-family: 'Roboto', serif;
  font-weight: 500;
  color: var(--full-white);
  line-height: 1.5rem;
  padding: 20px;
  opacity: 0.7;
  cursor: default;
}

/* MEDIA QUERIES */

@media (max-width: 992px) {
  .container {
    top: 200px;
    left: 100px;
    max-width: 500px;
  }
  h2 {
    font-size: 22px;
  }
  p {
    font-size: 0.9rem;
    padding: 15px;
  }
  .v-line ::before {
    height: 6.25rem;
  }
}

@media (max-width: 768px) {
  .container {
    top: 150px;
    left: 50px;
    max-width: 400px;
  }
  h2 {
    font-size: 18px;
  }
  p {
    font-size: 0.8rem;
    padding: 10px;
  }
  .v-line ::before {
    height: 5.5rem;
  }
  .wrapper {
    height: 450px;
  }
  section > img {
    padding-top: 80px;
  }
}

@media (max-width: 576px) {
  .container {
    top: 100px;
    left: 20px;
    max-width: 300px;
  }
  h2 {
    font-size: 16px;
  }
  p {
    font-size: 0.75rem;
    padding: 8px;
  }
  .v-line ::before {
    height: 5.2rem;
  }
  .wrapper {
    height: 400px;
  }
  section > img {
    padding-top: 60px;
  }
}
</style>
