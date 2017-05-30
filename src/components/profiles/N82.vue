<template>
  <div class="n82">
    <div>
      <img
          v-bind:src="profile.image"
          v-bind:width="profile.width"
          v-bind:height="profile.height"
          v-bind:style="{ minWidth: profile.width, minHeight: profile.height }" />
      <h2><a v-bind:href="url">{{ profile.title}}</a></h2>
      <p v-html="profile.snippet" />
    </div>
  </div>
</template>

<script>
export default {
  name: 'n82',
  props: ['profile', 'url'],
}
</script>

<style scoped>
.n82 {
  padding: 20px;
  clear: both;
}

.n82 img {
  float: right;
  margin: 5px;
}

.n82 p {
  padding: 0;
}

.n82 h2 {
  text-align: left;
}

.n82 p {
  font-size: .9375rem;
  line-height: 1.46667;
  text-align: left;
  color: #666;
}
</style>