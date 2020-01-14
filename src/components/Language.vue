<template>
  <div class="language">
    <ul>
      <li :class="language == 'val' ? 'active' : ''">
        <a href="#" @click.prevent="$emit('update:language', 'val')">Valencià</a>
      </li>
      <li :class="language == 'cas' ? 'active' : ''">
        <a href="#" @click.prevent="$emit('update:language', 'cas')">Castellano</a>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'language',

  props: {
    language: {
      type: String,
      default: 'val'
    }
  }
}
</script>

<style lang="scss" scoped>
  $gray: #DDD;
  $gray-light: #EEE;

  .language {
    text-align: center;
    margin-bottom: 2rem;
    border-bottom: 1px $gray solid;

    ul {
      margin-bottom: -2px;
    }

    li {
      display: inline-block;
      margin-left: 0;
      margin-bottom: 0;
      border: 1px transparent solid;

      a {
        display: block;
        padding: 1.25rem 2rem;
        font-size: 2rem;

        &:hover {
          background: $gray-light;
        }
      }
    }

    li.active {
      background: #FFF;
      border: 1px $gray solid;
      border-bottom: 0;

      a:hover {
        background: #FFF;
      }
    }
  }
</style>
