<template>
  <component v-if="type" :is="type" :profile="profile" :url="url"/>
</template>

<script>
import N81 from './profiles/N81';
import N82 from './profiles/N82';
import N85 from './profiles/N85';
import N06 from './profiles/N06';
import defaultProfile from './profiles/default';

export default {
  components: {
    N81,
    N82,
    N06,
    N85,
    defaultProfile,
  },
  name: 'item',
  props: ['content'],
  data() {
    return {
      type: null,
      profile: null,
      url: null,
    };
  },
  created() {
    this.type = Object.keys(this.content.profiles).pop();
    this.profile = this.type ? this.content.profiles[this.type] : this.content.default;
    this.url = this.content.url;
    this.type = this.type ? this.type : 'defaultProfile';
  }
}
</script>

<style scoped>
.content {
  margin: auto;
}
</style>