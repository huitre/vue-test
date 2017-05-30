<template>
  <div class="n81">
    <h2><a v-bind:href="url">{{ profile.title}}</a></h2>
    <img v-bind:src="profile.image" v-bind:width="profile.width" v-bind:height="profile.height" />
    <p v-html="profile.snippet" />
  </div>
</template>

<script>
export default {
  name: 'n81',
  props: ['profile', 'url'],
}
</script>

<style scoped>
.n81 {
  padding: 5px;
}

.n81 p {
  color: #666;
  text-align: left;
  padding: 5px;
}
</style>