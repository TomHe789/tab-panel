<template>
  <panel-item-wrapper panelTitle="模型参数">
    <template #panelBottom>
      <div class="data-setting">
        <slider-item
          name="scaleX"
          :value="panelData.slideX"
          :maxValue="panelData.maxValue"
        ></slider-item>
        <slider-item
          name="scaleY"
          :value="panelData.slideY"
          :maxValue="panelData.maxValue"
        ></slider-item>
        <slider-item
          name="scaleZ"
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
import SliderItem from './../components/SliderItem.vue'
import axios from 'axios'

const panelData = ref({})

axios.get('/dataSource/panelData.json').then(res => {
  if (res.status === 200) {
    panelData.value = res.data.modelParameter
  }
})
</script>

<style lang="less" scoped></style>
