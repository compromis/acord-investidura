<template>
  <div id="categories">
    <div class="row">
      <div v-for="category in categories" :key="category.id" class="category col-sm-4 col-lg-3">
        <a :href="'#' + category.slug" :class="'category-' + category.slug" v-smooth-scroll>
          {{ category.name }}
        </a>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'categories',

  props: {
    categories: Array
  }
}
</script>

<style lang="scss" scoped>

  /* Category colors */
  $financament:     #e28026;
  $dependencia:     #e07b26;
  $inversions:      #df7626;
  $deute:           #de7026;
  $agricultura:     #dd6a26;
  $hidriques:       #dc6526;
  $medi-ambient:    #db6027;
  $drets-socials:   #d95a27;
  $ap7:             #d85527;

  .category {
    margin-bottom: 2.5rem;

    a {
      display: block;
      height: 15rem;
      padding: 2rem;
      font-family: 'Compromis', sans-serif;
      font-size: 1.75rem;
      color: #FFF;
      border-width: 4px;
      border-style: solid;
      transition: 0.2s ease-in;

      &:hover {
        background: #FFF;
      }
    }
  }

  .category-financament {
    background: $financament;
    border-color: $financament;

    &:hover {
        color: $financament;
    }
  }
  .category-dependencia {
    background: $dependencia;
    border-color: $dependencia;

    &:hover {
        color: $dependencia;
    }
  }
  .category-inversions {
    background: $inversions;
    border-color: $inversions;

    &:hover {
        color: $inversions;
    }
  }
  .category-deute {
    background: $deute;
    border-color: $deute;

    &:hover {
        color: $deute;
    }
  }
  .category-agricultura {
    background: $agricultura;
    border-color: $agricultura;

    &:hover {
        color: $agricultura;
    }
  }
  .category-hidriques {
    background: $hidriques;
    border-color: $hidriques;

    &:hover {
        color: $hidriques;
    }
  }
  .category-medi-ambient {
    background: $medi-ambient;
    border-color: $medi-ambient;

    &:hover {
        color: $medi-ambient;
    }
  }
  .category-drets-socials {
    background: $drets-socials;
    border-color: $drets-socials;

    &:hover {
        color: $drets-socials;
    }
  }
  .category-ap7 {
    background: $ap7;
    border-color: $ap7;

    &:hover {
        color: $ap7;
    }
  }

  @media screen and (max-width: 768px) {
    .category {
      a {
        height: auto;
      }
    }
  }
</style>
