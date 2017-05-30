<template>
  <div class="home">
  <my-header />
  <loader v-show="loading"/>
  <h1>{{ title }}</h1>
  <block
    v-for="block in content"
    v-bind:block="block"
    v-bind:key="block.remoteId">
  </block>
  </div>
</template>

<script>
import loader from './Loader.vue';
import block from './Block.vue';
import myHeader from './Head.vue';
import axios from 'axios';

const OBJECT_PER_PAGE = 50;
let page = 1;
export default {
  name: 'home',
  components: {
    loader,
    block,
    myHeader,
  },
  data () {
    return {
      blocks: [],
      content: [],
      scrolled: 0,
      loading: true,
      title: '',
    }
  },
  watch: {
  },
  methods: {
    load() {
      const self = this;
      axios.get('http://demo5388217.mockable.io/').then(response => {
        window.setTimeout(() => {
          self.loading = false;
          self.blocks = [].concat(response.data.page.rankings.News.blocs);
          self.title = response.data.page.default.title;
          self.content = response.data.page.rankings.News.blocs.slice(0, OBJECT_PER_PAGE);
        }, 1000);
      });
    },
    fetchMore() {
      const self = this;
      self.loading = true;
      window.setTimeout(() => {
        self.content = [].concat(this.content, this.blocks.slice(page, OBJECT_PER_PAGE));
        self.loading = false;
        page += 1;
      }, 300);
    },
    handleScroll () {
      if (window.scrollY + window.innerHeight >= window.document.body.clientHeight) {
        // this.fetchMore();
      }
    }
  },
  created () {
    window.addEventListener('scroll', this.handleScroll);
    this.load();
  },
  destroyed () {
    window.removeEventListener('scroll', this.handleScroll);
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>
  .figh__full {
    background-color: #3368ad !important;
  }

h1 {
  font-size: 2.5rem;
  line-height: 1.15;
  background: #fff;
  padding: 15px;
  font-family: MuseoSlab500,Trebuchet MS,Arial,Helvetica,sans-serif;
}
</style>
