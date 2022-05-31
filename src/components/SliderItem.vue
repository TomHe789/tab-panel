<template>
  <div class="setting-item">
    <div class="item-name">{{ name }}</div>
    <el-slider v-model="value" :max="maxValue" />
    <div class="item-data">{{ value }}</div>
  </div>
</template>

<script setup>
import { ref } from 'vue'

defineProps({
  name: String,
  value: Number,
  maxValue: Number,
})
</script>

<style lang="less" scoped>
.setting-item {
  display: flex;
  align-items: center;
  justify-content: space-around;
  padding: 5px 0;
  border-bottom: 1px solid rgba(255, 255, 255, 0.4);
  .el-slider {
    width: 38%;
    /deep/ .el-slider__runway {
      height: 100%;
      background-color: rgb(48, 48, 48);
      border-radius: 0;
      .el-slider__bar {
        height: 100%;
        border-radius: 0;
      }
    }
    /deep/ .el-slider__button-wrapper {
      display: none;
    }
  }
  .item-name {
    width: 80px;
    padding-left: 5px;
  }
  .item-data {
    width: 80px;
    height: 32px;
    line-height: 32px;
    text-align: center;
    background-color: rgb(48, 48, 48);
    color: #409eff;
  }
}
</style>
