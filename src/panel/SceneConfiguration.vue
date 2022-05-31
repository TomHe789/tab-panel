<template>
  <panel-item-wrapper panelTitle="场景配置">
    <template #panelBottom>
      <color-picker-item color="#409EFF" />
      <div class="data-setting">
        <slider-item name="x" :value="150" :maxValue="300"></slider-item>
        <slider-item name="y" :value="60" :maxValue="300"></slider-item>
        <slider-item name="z" :value="100" :maxValue="300"></slider-item>
      </div>
    </template>
  </panel-item-wrapper>
</template>

<script setup>
import { ref } from 'vue'
import PanelItemWrapper from './../components/PanelItemWrapper.vue'
import ColorPickerItem from './../components/ColorPickerItem.vue'
import SliderItem from './../components/SliderItem.vue'
</script>

<style lang="less" scoped></style>
