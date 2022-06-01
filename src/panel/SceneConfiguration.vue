<template>
  <panel-item-wrapper panelTitle="场景配置">
    <template #panelBottom>
      <color-picker-item :color="panelData.color" />
      <div class="data-setting">
        <slider-item
          name="x"
          :value="panelData.slideX"
          :maxValue="panelData.maxValue"
        ></slider-item>
        <slider-item
          name="y"
          :value="panelData.slideY"
          :maxValue="panelData.maxValue"
        ></slider-item>
        <slider-item
          name="z"
          :value="panelData.slideZ"
          :maxValue="panelData.maxValue"
        ></slider-item>
      </div>
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
    panelData.value = res.data.seneConfiguration
  }
})
</script>

<style lang="less" scoped></style>
