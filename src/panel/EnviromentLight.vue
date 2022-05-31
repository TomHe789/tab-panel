<template>
  <panel-item-wrapper panelTitle="环境光">
    <template #panelBottom>
      <div class="data-setting">
        <slider-item name="intensity" :value="1" :maxValue="5"></slider-item>
      </div>
      <color-picker-item color="#fff" />
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
