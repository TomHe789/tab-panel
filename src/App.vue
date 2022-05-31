<script setup>
import TopPanel from './components/TopPanel.vue'
import TabPanel from './components/TabPanel.vue'
</script>

<template>
  <TopPanel/>
  <TabPanel/>
</template>

<style>
* {
  margin: 0;
  padding: 0;
}
body {
  background-color: rgb(240, 240, 240);
}
.data-setting {
  border-left: 3px #409eff solid;
}
</style>
