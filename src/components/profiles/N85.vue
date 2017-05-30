<template>
  <div class="n85">
    <h2><a v-bind:href="url">{{ profile.title}}</a></h2>
    <img v-bind:src="profile.image" v-bind:width="profile.width" v-bind:height="profile.height" />
    <p v-html="profile.snippet" />
  </div>
</template>

<script>
export default {
  name: 'n85',
  props: ['profile', 'url'],
}
</script>

<style scoped>
.n85 {
  padding: 20px;
}


.n85 h2 {
  font-size: 1.75rem;
}

.n85 img {
  margin-bottom: 15px;
}

.n85 p {
  color: #666;
  text-align: left;
  font-size: .9375rem;
  line-height: 1.46667;
}
</style>