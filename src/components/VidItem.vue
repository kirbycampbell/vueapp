<template>
  <div class="vid-item" v-bind:class="{'is-complete':vid.completed}">
    <p>
      <input type="checkbox" v-on:change="markComplete">

      <youtube :video-id="vid.title"></youtube>
      <button @click="$emit('del-vid', vid.id)" class="del">X</button>
    </p>
  </div>
</template>

<script>
import Vue from "vue";
import VueYouTubeEmbed from "vue-youtube-embed";
Vue.use(VueYouTubeEmbed);
export default {
  name: "VidItem",
  props: ["vid"],
  methods: {
    markComplete() {
      this.vid.completed = !this.vid.completed;
    }
  }
};
</script>

<style scoped>
.vid-item {
  background: #f4f4f4;
  padding: 10px;
  border-bottom: 1px;
}

.is-complete {
  text-decoration: line-through;
}

.del {
  background: red;
  color: #fff;
  border: none;
  padding: 5px 9px;
  border-radius: 50%;
  cursor: pointer;
  float: right;
}
</style>