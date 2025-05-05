<script setup>
import articlesFutura from '../assets/data/articles.json'

const categoriesColors = {
  sciences: ['#be80ff', '#6325ff'],
  sante: ['#ff6b9f', '#ff4e52'],
  planete: ['#9fcb5c', '#069849'],
  maison: ['#fa9761', '#ff5957'],
  tech: ['#49adfa', '#2a3df7'],
}

function getGradientStyle(category) {
  const colors = categoriesColors[category.toLowerCase()]
  if (!colors) return {}
  return {
    background: `linear-gradient(90deg, ${colors[0]}, ${colors[1]})`,
    WebkitBackgroundClip: 'text',
    WebkitTextFillColor: 'transparent',
  }
}
</script>

<template>
  <section class="gridContainer">
    <div v-for="article in articlesFutura.articlesList" :key="article.id" class="containerArticle">
      <img :src="article.image" :alt="article.title" />
      <h3>
        <span :style="getGradientStyle(article.category)">{{
          article.category.toUpperCase()
        }}</span>
        {{ article.subCategory.toUpperCase() }}
      </h3>
      <h4>{{ article.title }}</h4>
      <p>{{ article.date }}</p>
    </div>
  </section>
</template>

<style scoped>
.gridContainer {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 30px;
  max-width: 1300px;
  margin: 0 auto;
  padding: 50px 0;
}
.containerArticle {
  height: 480px;
  background-color: var(--bckg-main);
  color: var(--full-black);
  overflow: hidden;
  display: flex;
  flex-direction: column;
}
img {
  width: 100%;
  height: 320px;
  object-fit: cover;
}
h3 {
  display: flex;
  gap: 10px;
  font-size: small;
  padding: 15px 0 5px;
  width: fit-content;
  margin: 0px;
  color: var(--full-black);
  cursor: default;
}
h3 > span {
  font-size: small;
  font-weight: 600;
}
h4 {
  font-family: 'Merriweather', serif;
  font-size: 16px;
  font-weight: 600;
  margin: 0;
  color: var(--full-black);
  line-height: 1.4;
  word-break: break-word;
  cursor: pointer;
}

p {
  font-family: 'Roboto', serif;
  font-weight: 500;
  font-size: small;
  color: var(--full-black);
  line-height: 1.5rem;
  opacity: 0.4;
  padding-top: 5px;
  cursor: default;
}

/* --- MEDIA QUERIES */
@media (max-width: 1200px) {
  .gridContainer {
    grid-template-columns: repeat(3, 1fr);
    gap: 20px;
    padding: 30px;
    justify-content: center;
    width: 90%;
  }
  .containerArticle {
    height: 450px;
  }
  img {
    height: 300px;
  }
}

@media (max-width: 992px) {
  .gridContainer {
    grid-template-columns: repeat(2, 1fr);
    gap: 15px;
    padding: 30px 20px;
    justify-content: center;
    width: 90%;
  }
  .containerArticle {
    height: 420px;
  }
  img {
    height: 280px;
  }
  h4 {
    font-size: 14px;
  }
  p {
    font-size: 0.7rem;
  }
}

@media (max-width: 768px) {
  .gridContainer {
    grid-template-columns: repeat(1, 1fr);
    gap: 20px;
    padding: 30px 0px;
    justify-content: center;
  }
  .containerArticle {
    height: auto;
    max-width: 100%;
    flex-direction: column;
    align-items: stretch;
  }

  img {
    width: 100%;
    max-height: none;
    height: auto;
  }

  .containerArticle > div {
    padding-left: 15px;
  }
  h3 {
    font-size: 0.7rem;
    padding: 5px 0;
  }
  h4 {
    font-size: 1.1rem;
  }
  p {
    font-size: 0.8rem;
  }
}

@media (max-width: 576px) {
  h4 {
    font-size: 0.9rem;
  }
  p {
    font-size: 0.55rem;
  }
}
</style>
