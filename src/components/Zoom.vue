<template>
  <div class="zoom">
    <div class="zoom__first">
      <h2>{{ first.default.title }}</h2>
      <img v-bind:src="first.default.image" />
      <p v-html="first.default.snippet" />
    </div>
    <ul class="zoom__other">
      <li v-for="item in list" class="zoom__item">
      <img v-bind:src="item.default.image" />
      <h2>{{ item.default.title }}</h2>
      </li>
    </ul>
  </div>
</template>

<script>

export default {
  name: 'zoom',
  props: ['content'],
  data() {
    return {
      first: null,
      list: null,
    };
  },
  created() {
    this.first = this.content.pop();
    this.list = this.content;
  }
}
</script>

<style scoped>
.zoom {
  background: #f3e7e2;
  border-color: #dbd0cb;
}

.zoom__first {
  float: left;
  width: 49.15254%;
  padding: 15px;
  color: #666;
}

.zoom__first h2 {
  font-size: 1.125rem;
  color: #003872;
}

.zoom__first p {
  padding: 5px 0 5px;
}

.zoom__first img, .zoom__item img {
  width: 100%;
}

.zoom__other {
  float: right;
  width: 45%;
  margin-top: 15px;
}
.zoom__item {
  margin: 0 0 10px;
  padding: 10px;
  background: #ececec;
}

.zoom__item h2 {
  font-size: 1rem;
}

.zoom__item img {
  float: right;
  width: 45%;
}
</style>