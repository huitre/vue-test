<template>
  <div class="n06">
    <img v-bind:src="profile.image" v-bind:width="profile.width" v-bind:height="profile.height" />
    <h2>{{ profile.title}}</h2>
    <p v-html="profile.snippet" />
  </div>
</template>

<script>
export default {
  name: 'N06',
  props: ['profile', 'url'],
}
</script>

<style scoped>
.n06 {

}

.n06 img {
  width: 100%;
}
</style>