<template>
  <Fragment>
    <panel-item-wrapper panelTitle="材质选择">
      <template #panelBottom>
        <div class="data-setting">
          <div class="setting-item">
            <div class="item-name">Material</div>
            <el-select v-model="selectValue" placeholder="Select" size="small">
              <el-option
                v-for="(item, index) in panelData.optionData"
                :key="item.value"
                :label="item.label"
                :value="item.value"
                @click="clickHandle(index)"
              />
            </el-select>
          </div>
        </div>
      </template>
    </panel-item-wrapper>
    <template v-if="selectValue">
      <panel-item-wrapper :panelTitle="selectValue">
        <template #panelBottom>
          <color-picker-item
            :color="panelData.optionData[selectIndex].detailData.color"
          />
          <div class="data-setting">
            <slider-item
              name="x"
              :value="panelData.optionData[selectIndex].detailData.slideX"
              :maxValue="panelData.optionData[selectIndex].detailData.maxValue"
            ></slider-item>
            <slider-item
              name="y"
              :value="panelData.optionData[selectIndex].detailData.slideY"
              :maxValue="panelData.optionData[selectIndex].detailData.maxValue"
            ></slider-item>
            <slider-item
              name="z"
              :value="panelData.optionData[selectIndex].detailData.slideZ"
              :maxValue="panelData.optionData[selectIndex].detailData.maxValue"
            ></slider-item>
          </div>
        </template>
      </panel-item-wrapper>
    </template>
  </Fragment>
</template>

<script setup>
import { ref, inject, onMounted, reactive } from 'vue'
import PanelItemWrapper from './../components/PanelItemWrapper.vue'
import ColorPickerItem from './../components/ColorPickerItem.vue'
import SliderItem from './../components/SliderItem.vue'
import axios from 'axios'

const selectValue = ref('')

const selectIndex = ref(-1)

const panelData = ref({})

const clickHandle = index => {
  selectIndex.value = index
}

axios.get('/dataSource/panelData.json').then(res => {
  if (res.status === 200) {
    panelData.value = res.data.materialSelect
  }
})
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
