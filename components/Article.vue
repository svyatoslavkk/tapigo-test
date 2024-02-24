<template>
  <div>
    <Header />
    <div v-for="(item, index) in articles" :key="index" class="article">
      <img :src="item.image" />
      <div class="article-content">
        <span>{{ item.description }}</span>
        <div>
          <p>{{ item.paragraph_1 }}</p>
          <p>{{ item.paragraph_2 }}</p>
          <p v-if="item.paragraph_3">{{ item.paragraph_3 }}</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import { articles } from '~/constants';

export default {
  data() {
    return {
      articles: articles,
    };
  },
};
</script>

<style>

</style>