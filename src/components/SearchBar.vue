<template>
  <form class="search-bar"
        @submit.prevent="search()">
    <input type="text"
           placeholder="Search"
           v-model="filter" />
    <button>
      <icon name="magnify" />
    </button>
  </form>
</template>
<script>
import Icon from '@/components/Icon.vue';

export default {
  name: 'search-bar',
  components: {
    Icon,
  },

  data() {
    return {
      filter: '',
    };
  },

  methods: {
    search() {
      /* eslint no-console: ["error", { allow: ["warn", "error", "log"] }] */
      console.log('do search');
    },
  },
};
</script>
<style lang="scss" scoped>
  .search-bar {
    position: absolute;
    top: 0;
    right: 0;
    justify-content: flex-end;
    align-items: center;

    input {
      margin: 1rem;
      background: transparent;
      color: #fff;
      font-size: 1.6rem;
      width: 10rem;
      opacity: .6;

      &::placeholder {
        color: #737373;
        text-transform: uppercase;
      }
    }

    button {
      border: none;
      background: transparent;
      padding: 0;
    }
  }

  @media (min-width: 1400px) {
    .search-bar {
      display: flex;
    }
  }

  @media (max-width: 800px) {
    .search-bar{
      display: flex;
      align-items: center;
      input {
        margin: 0 1rem 0 0;
      }
    }
  }
</style>
