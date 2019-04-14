<template>
  <div>
    <div v-bind:key="vid.id" v-for="vid in vids">
      <VidItem v-bind:vid="vid" v-on:del-vid="$emit('del-vid', vid.id)"/>
    </div>
  </div>
</template>

<script>
import VidItem from "./VidItem.vue";

export default {
  name: "Vids",
  components: {
    VidItem
  },
  props: ["vids"]
};
</script>

<style scoped>
</style>
