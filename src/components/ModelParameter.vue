<template>
  <panel-item-wrapper panelTitle="模型参数">
    <template #panelBottom>
      <div class="data-setting">
        <slider-item name="scaleX" :value="1" :maxValue="5"></slider-item>
        <slider-item name="scaleY" :value="1" :maxValue="5"></slider-item>
        <slider-item name="scaleZ" :value="1" :maxValue="5"></slider-item>
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
