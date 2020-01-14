<template>
  <div class="accountable-gov">
    <div class="header">
      <h2><img src="./assets/logo.png" alt="Seguiment de l'Acord d'Investidura" /></h2>
    </div>
    <language :language.sync="language" />
    <categories :categories="categories" />
    <hr />
    <document :categories="categories" :document="document" :language="language" />
  </div>
</template>

<script>
import Categories from './components/Categories.vue'
import Document from './components/Document.vue'
import Language from './components/Language.vue'

import dataVal from './data/data.val.json'
import dataCas from './data/data.cas.json'

export default {
  name: 'app',

  components: {
    Categories,
    Document,
    Language
  },

  data() {
    return {
      document: [],
      categories: [],
      language: 'val'
    }
  },

  watch: {
    language: function(newLang) {
      if(newLang == 'cas') {
        this.document = dataCas.document;
        this.categories = dataCas.categories;
      } else {
        this.document = dataVal.document;
        this.categories = dataVal.categories;
      }
    }
  },

  mounted() {
    this.document = dataVal.document
    this.categories = dataVal.categories
  }
}
</script>

<style lang="scss">
  .accountable-gov .header {
    text-align: center;
    font-size: 3.5rem;
    margin: 2rem 0 1rem;
    padding: 0 3rem;

    img {
      width: 100%;
      max-width: 800px;
    }
  }

  .header-page {
    h1 {
      display: none;
    }
  }

  .page-nav {
    margin-bottom: 10px;
  }
</style>
