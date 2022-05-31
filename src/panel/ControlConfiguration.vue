<template>
  <panel-item-wrapper panelTitle="控制配置">
    <template #panelBottom>
      <div class="data-setting">
        <slider-item
          name="autoRotate"
          :value="1"
          :maxValue="2"
        ></slider-item>
        <slider-item
          name="minDistance"
          :value="50"
          :maxValue="1000"
        ></slider-item>
        <slider-item
          name="maxDistance"
          :value="150"
          :maxValue="1000"
        ></slider-item>
      </div>
      <div class="setting-item">
        
      </div>
    </template>
  </panel-item-wrapper>
</template>

<script setup>
import { ref } from 'vue'
import PanelItemWrapper from './../components/PanelItemWrapper.vue'
import SliderItem from './../components/SliderItem.vue'
</script>

<style lang="less" scoped></style>
