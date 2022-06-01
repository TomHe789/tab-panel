<template>
  <panel-item-wrapper panelTitle="环境光">
    <template #panelBottom>
      <div class="data-setting">
        <slider-item
          name="intensity"
          :value="panelData.slideIntensity"
          :maxValue="panelData.maxValue"
        ></slider-item>
      </div>
      <color-picker-item :color="panelData.color" />
    </template>
  </panel-item-wrapper>
</template>

<script setup>
import { ref } from 'vue'
import PanelItemWrapper from './../components/PanelItemWrapper.vue'
import ColorPickerItem from './../components/ColorPickerItem.vue'
import SliderItem from './../components/SliderItem.vue'

import axios from 'axios'

const panelData = ref({})

axios.get('/dataSource/panelData.json').then(res => {
  if (res.status === 200) {
    panelData.value = res.data.enviromentLight
  }
})
</script>

<style lang="less" scoped></style>
