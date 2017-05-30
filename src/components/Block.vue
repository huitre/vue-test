<template>
  <div :class="'block block--' + profile">
    <div class="block__head">
      <h1 :class="type"> {{ titre }} </h1>
    </div>
    <div class="block__content">
      <item
        v-if="profile !== 'zoom'"
        v-for="item in block.feed"
        v-bind:content="item"
        v-bind:key="block.remoteId"
        v-bind:class="getClassName(item.type)"/>
      <zoom
        v-if="profile === 'zoom'"
        v-bind:content="block.feed"
        />
      </div>
  </div>
</template>

<script>
import item from './Item';
import zoom from './Zoom';

export default {
  name: 'block',
  components: {
    item,
    zoom,
  },
  props: ['block'],
  data() {
    return {
      type: this.block.type,
      titre: this.block.titre,
      profile: this.block.profil
    }
  },
  methods: {
    getClassName(name) {
      return name.replace(/ /g, '-').toLowerCase()
    }
  },
  created() {
  }
}
</script>

<style scoped>
.block {
  background: #fff;
  position: relative;
  padding-bottom: 15px;
}

.TrancheEdito {
  color: #fff;
  border-color: #6d2928;
  background-color: #792e2c;
  font-family: MuseoSlab500,Trebuchet MS,Arial,Helvetica,sans-serif;
  font-size: 1rem;
  line-height: 1.25;
}

.block--zoom {
  padding: 15px 10px;
  text-align: left;
  border-top: 1px solid #d6d6d6;
  border-bottom: 1px solid #d6d6d6;
  background-color: #f2f2f2;
}

.block--zoom .block__content {
  display: flex;
}


.block-zoom::after {
  clear: both;
}

.block--ensemble {
  text-align: left;
  border-top: 1px solid #d6d6d6;
  border-bottom: 1px solid #d6d6d6;
  background-color: #f2f2f2;
}

.block--ensemble::before {
    content: ' ';
    width: 10px;
    height: 100%;
    background-color: #792e2c;
    position: absolute;
    left: -10px;
    top: -4px;
    box-shadow: -1px 0px 5px rgba(0, 0, 0, 0.3);
}

.block--ensemble h1 {
  box-shadow: 0px -1px 5px rgba(0, 0, 0, 0.3);
  font-size: 1rem;
  width: auto;
  display: inline;
  text-align: left;
  padding: 5px;
}
</style>