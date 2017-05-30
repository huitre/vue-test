<template>
  <div class="default">
    <h2><a v-bind:href="url">{{ profile.title}}</a></h2>
    <img v-bind:src="profile.image" v-bind:width="profile.width" v-bind:height="profile.height" />
    <p v-html="profile.snippet" />
  </div>
</template>

<script>
export default {
  name: 'defaultProfile',
  props: ['profile', 'url'],
}
</script>

<style scoped>
.default {
  padding: 20px;
}


.default h2 {
  font-size: 1.75rem;
}

.default img {
  margin-bottom: 15px;
}

.default p {
  color: #666;
  text-align: left;
  font-size: .9375rem;
  line-height: 1.46667;
}

.block--zoom .feed.art .default img {
  width: 100%;
  height: 100%;
}

</style>