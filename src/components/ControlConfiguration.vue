<template>
  <panel-item-wrapper panelTitle="控制配置">
    <template #panelBottom>
      <div class="data-setting">
        <slider-item
          name="autoRotateSp.."
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
      
    </template>
  </panel-item-wrapper>
</template>

<script setup>
import { ref } from 'vue'
import PanelItemWrapper from './PanelItemWrapper.vue'
import ColorPickerItem from './ColorPickerItem.vue'
import SliderItem from './SliderItem.vue'
</script>

<style lang="less" scoped></style>
