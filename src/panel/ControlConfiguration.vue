<template>
  <panel-item-wrapper panelTitle="控制配置">
    <template #panelBottom>
      <div class="data-setting">
        <slider-item
          name="autoRotate"
          :value="panelData.slieAutoRotate"
          :maxValue="panelData.maxValue"
        ></slider-item>
        <slider-item
          name="minDistance"
          :value="panelData.slideMinDistance"
          :maxValue="panelData.maxValue"
        ></slider-item>
        <slider-item
          name="maxDistance"
          :value="panelData.slideMaxDistance"
          :maxValue="panelData.maxValue"
        ></slider-item>
      </div>
      <div class="setting-item">
        <div class="item-name">autoRotate</div>
        <input type="checkbox" :checked="panelData.isChecked"/>
      </div>
    </template>
  </panel-item-wrapper>
</template>

<script setup>
import { ref } from 'vue'
import PanelItemWrapper from './../components/PanelItemWrapper.vue'
import SliderItem from './../components/SliderItem.vue'
import axios from 'axios'

const panelData = ref({})

axios.get('/dataSource/panelData.json').then(res => {
  if (res.status === 200) {
    panelData.value = res.data.controlConfiguration
  }
})
</script>

<style lang="less" scoped>
.setting-item {
  display: flex;
  align-items: center;
  padding: 5px 0;
  border-bottom: 1px solid rgba(255, 255, 255, 0.4);
  .item-name {
    width: 140px;
    padding-left: 15px;
  }
  input {
    position: relative;
    left: -40px;
  }
}
</style>
