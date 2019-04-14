<template>
  <div id="app">
    <Header/>
    <AddVid v-on:add-vid="addVid"/>
    <Vids v-bind:vids="vids" v-on:del-vid="deleteVid"/>
  </div>
</template>

<script>
import Header from "./components/layout/Header";
import Vids from "./components/Vids";
import AddVid from "./components/AddVid";

export default {
  name: "app",
  components: {
    Header,
    Vids,
    AddVid
  },
  data() {
    return {
      vids: []
    };
  },
  methods: {
    deleteVid(id) {
      this.vids = this.vids.filter(vid => vid.id !== id);
    },
    addVid(newVid) {
      //const { title, completed } = newVid;
      this.vids = [...this.vids, newVid];
    }
  }
};
</script>

<style>
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}
body {
  font-family: Arial, Helvetica, sans-serif;
  line-height: 1.4;
}

.btn {
  display: inline-block;
  border: none;
  background: #555;
  color: #fff;
  padding: 7px 20px;
  cursor: pointer;
}

.btn:hover {
  background: #666;
}
</style>
