<template>
  <div>
    <Header />
    <article class="column-center main">
      <div class="pre-header">
        <div class="path">
          <button class="gray-text">Журнал</button>
          <span class="gray-text">/</span>
          <button class="gray-text">Статьи</button>
          <span class="gray-text">/</span>
          <button class="default-text">Бенуа — идеолог новой художественной эпохи</button>
        </div>
        <div></div>
      </div>
      <div class="column-center content">
        <img class="img" :src="openImage" />
        <h2>{{ articleTitle }}</h2>
        <div class="column-center quotes-block">
          <p>{{ articleQuotes }}</p>
          <span>{{ articleQuotesAuthor }}</span>
        </div>
        <div v-for="(item, index) in articles" :key="index" class="column-center article">
          <div class="column-center img-block" :style="{ maxWidth: item.imageWidth + 'px' }">
            <img v-if="item.image" class="img" :src="item.image" />
            <span v-if="item.description" class="description">{{ item.description }}</span>
          </div>
          <div class="article-content">
            <div class="paragraphs">
              <p>{{ item.paragraph_1 }}</p>
              <p>{{ item.paragraph_2 }}</p>
              <p v-if="item.paragraph_3">{{ item.paragraph_3 }}</p>
            </div>
          </div>
        </div>
        <footer class="footer-text">Автор: <button>Журнал Тапиго</button></footer>
      </div>
    </article>
  </div>
</template>

<script>
import { articles } from '~/constants';
import { openImage } from '~/constants';
import { articleTitle } from '~/constants';
import { articleQuotes } from '~/constants';
import { articleQuotesAuthor } from '~/constants';

export default {
  data() {
    return {
      articles: articles,
      openImage: openImage,
      articleTitle: articleTitle,
      articleQuotes: articleQuotes,
      articleQuotesAuthor: articleQuotesAuthor,
    };
  },
};
</script>

<style scoped>
  h2 {
    font-size: 34px;
    font-weight: 700;
  }
  button {
    cursor: pointer;
  }
  .column-center {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
  }
  .content, .pre-header, .img {
    max-width: 950px;
  }
  .paragraphs, .article {
    max-width: 825px;
  }
  .footer-text, .footer-text button, .default-text, .gray-text, .description {
    font-size: 13px;
  }
  .main {
    gap: 32px;
    padding: 75px 16px 105px 16px;
    margin: 0;
  }
  .pre-header {
    display: flex;
    align-items: center;
    justify-content: space-between;
    width: 100%;
  }
  .content {
    gap: 32px;
  }
  .quotes-block {
    text-align: center;
    gap: 0.5rem;
    width: 80%;
  }
  .quotes-block p {
    font-size: 20px;
    font-weight: 500;
    font-style: italic;
  }
  .article {
    gap: 40px;
  }
  .path {
    display: flex;
    flex-wrap: wrap;
    column-gap: 0.5rem;
  }
  .img-block {
    gap: 8px;
    width: 100%;
  }
  .img {
    border-radius: 8px;
    width: 100%;
  }
  .description {
    color: #c2c2c7;
    font-style: italic;
    width: 70%;
    text-align: center;
  }
  .paragraphs {
    display: flex;
    flex-direction: column;
    gap: 48px;
  }
  .gray-text {
    color: #6a7280;
  }
  .gray-text:hover,
  .gray-text:active,
  .gray-text:focus {
    color: #000;
  }
  .default-text {
    color: #000;
  }
  .footer-text {
    color: #c2c2c7;
    font-style: italic;
  }
  .footer-text button {
    font-style: italic;
    color: #008afe;
    text-decoration: underline;
    transition: 0.3s ease;
  }
  .footer-text button:hover {
    color: #000;
  }
</style>