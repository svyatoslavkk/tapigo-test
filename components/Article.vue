<template>
  <div>
    <Header />
    <article class="main">
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
      <div class="content">
        <img class="art-img" :src="openImage" />
        <h2>{{ articleTitle }}</h2>
        <div class="quotes-block">
          <p>{{ articleQuotes }}</p>
          <span>{{ articleQuotesAuthor }}</span>
        </div>
        <div v-for="(item, index) in articles" :key="index" class="article">
          <div class="img" :style="{ maxWidth: item.imageWidth + 'px' }">
            <img v-if="item.image" class="art-img" :src="item.image" />
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

<style>
  h2 {
    font-size: 34px;
    font-weight: 700;
  }
  button {
    cursor: pointer;
  }
  .quotes-block {
    display: flex;
    flex-direction: column;
    text-align: center;
    gap: 0.5rem;
    width: 80%;
  }
  .quotes-block p {
    font-size: 20px;
    font-weight: 500;
    font-style: italic;
  }
  .path {
    display: flex;
    flex-wrap: wrap;
    column-gap: 0.5rem;
    font-size: 15px;
  }
  .content {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    gap: 32px;
    max-width: 950px;
  }
  .link:hover {
    color: #000;
  }
  .img {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    gap: 8px;
    width: 100%;
  }
  .art-img {
    border-radius: 8px;
    max-width: 950px;
    width: 100%;
  }
  .description {
    color: #c2c2c7;
    font-style: italic;
    font-size: 13px;
    width: 70%;
    text-align: center;
  }
  .main {
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 32px;
    padding: 75px 16px 105px 16px;
    margin: 0;
  }
  .article {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    gap: 40px;
    max-width: 825px;
  }
  .paragraphs {
    max-width: 825px;
    display: flex;
    flex-direction: column;
    gap: 48px;
  }
  .pre-header {
    display: flex;
    align-items: center;
    justify-content: space-between;
    max-width: 950px;
    width: 100%;
  }
  .gray-text {
    font-size: 14px;
    color: #6a7280;
  }
  .gray-text:hover,
  .gray-text:active,
  .gray-text:focus {
    color: #000;
  }
  .default-text {
    font-size: 14px;
    color: #000;
  }
  .footer-text {
    color: #c2c2c7;
    font-style: italic;
    font-size: 13px;
  }
  .footer-text button {
    font-style: italic;
    font-size: 13px;
    color: #008afe;
    text-decoration: underline;
    transition: 0.3s ease;
  }
</style>