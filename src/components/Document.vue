<template>
  <div class="document">
    <div v-for="category in categories" :key="category.id" :id="category.slug" class="category">
      <div class="category-header">
        <h3>{{ category.name }}</h3>
      </div>
      <ul class="points">
        <li v-for="point in document" :key="point.text" v-if="point.category === category.id" class="point">
          <div class="text">{{ point.text }}</div>
          <div v-if="point.status == 'DONE'" class="status status-done">
            <span class="glyphicon glyphicon-ok"></span>
            <span v-if="language == 'cas'">Hecho</span>
            <span v-else>Fet</span>
          </div>
          <div v-if="point.status == 'PENDING'" class="status status-pending">
            <span class="glyphicon glyphicon-time"></span>
            <span v-if="language == 'cas'">Pendiente</span>
            <span v-else>Pendent</span>
          </div>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  name: 'document',

  props: {
    document: Array,
    categories: Array,
    language: {
      type: String,
      default: 'val'
    }
  },
}
</script>

<style lang="scss" scoped>
  .points {
    li {
      display: flex;
      align-items: center;
      font-size: 1.75rem;
      margin: 0;
      padding: 0;
      border-bottom: 1px #E1E2E3 solid;
      padding: 15px 0;
      position: relative;
      transition: 0.2s ease-in;
    }
  }

  .text {
    padding-right: 1rem;
  }

  .status {
    flex-shrink: 0;
    flex-grow: 0;
    margin-left: auto;
    background: #DDD;
    padding: 0.5rem 2rem;
    font-size: 1.75rem;
    color: #FFF;
    white-space: nowrap;
    cursor: default;
    display: inline-block;
    width: 160px;
    text-align: center;
    position: relative;
  }

  .status-done {
    background: #26AC5B;
  }

  .status-pending {
    background: #F39B00;
  }

  .category-header {
    display: flex;
    align-items: center;
    margin-top: 5rem;

    h3 {
      font-size: 30px;
      background: linear-gradient(270deg, #D4432F, #E28333);
      line-height: 125%;
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      display: inline-block;
      margin-right: auto;
      padding-bottom: 1rem;
    }

    .back-to-top {
      font-size: 1.75rem;
      color: #888;
    }
  }

  .glyphicon {
    margin-right: .5rem;
  }

  @media screen and (max-width: 768px) {
    .category-header {
      flex-direction: column;

      h3 {
        order: 2;
        margin-top: 5rem;
      }

      .back-to-top {
        order: 1;
      }
    }

    .category:first-child {
      h3 {
        margin-top: 0;
      }

      .back-to-top {
        display: none;
      }
    }
  }
</style>
