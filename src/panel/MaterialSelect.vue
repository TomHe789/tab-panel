<template>
  <Fragment>
    <panel-item-wrapper panelTitle="材质选择">
      <template #panelBottom>
        <div class="data-setting">
          <div class="setting-item">
            <div class="item-name">Material</div>
            <el-select v-model="value" placeholder="Select" size="small">
              <el-option
                v-for="item in options"
                :key="item.value"
                :label="item.label"
                :value="item.value"
              />
            </el-select>
          </div>
        </div>
      </template>
    </panel-item-wrapper>
    <panel-item-wrapper :panelTitle="value">
      <template #panelBottom>
        <color-picker-item color="#409EFF" />
        <div class="data-setting">
          <slider-item name="x" :value="150" :maxValue="300"></slider-item>
          <slider-item name="y" :value="60" :maxValue="300"></slider-item>
          <slider-item name="z" :value="100" :maxValue="300"></slider-item>
        </div>
      </template>
    </panel-item-wrapper>
  </Fragment>
</template>

<script setup>
import { ref, inject, onMounted, toRef } from 'vue'
import PanelItemWrapper from './../components/PanelItemWrapper.vue'
import ColorPickerItem from './../components/ColorPickerItem.vue'
import SliderItem from './../components/SliderItem.vue'

const value = ref('')

const options = [
  {
    value: 'Option1',
    label: 'Option1',
  },
  {
    value: 'Option2',
    label: 'Option2',
  },
  {
    value: 'Option3',
    label: 'Option3',
  },
  {
    value: 'Option4',
    label: 'Option4',
  },
  {
    value: 'Option5',
    label: 'Option5',
  },
]

// const panelData = inject('panelData')

// onMounted(() => {
//   console.log('123123123',  panelData, panelData.value)
// })
</script>

<style lang="less" scoped>
.setting-item {
  display: flex;
  align-items: center;
  justify-content: space-around;
  padding: 5px 0;
  border-bottom: 1px solid rgba(255, 255, 255, 0.4);
  .item-name {
    width: 80px;
  }
}
</style>
