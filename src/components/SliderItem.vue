<template>
  <div class="setting-item">
    <div class="item-name">{{ name }}</div>
    <el-slider v-model="value" :max="maxValue" show-input />
    <!-- <div class="item-data">{{ value }}</div> -->
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
     :deep(.el-slider__runway) {
      height: 100%;
      background-color: rgb(48, 48, 48);
      border-radius: 0;
      .el-slider__bar {
        height: 100%;
        border-radius: 0;
      }
    }
     :deep(.el-input-number) {
      width: 50px;
      .el-input__wrapper {
        padding: 0;
      }
    }
     :deep(.el-slider__button-wrapper) {
      display: none;
    }
     :deep(span) {
      display: none;
    }
     :deep(.show-input) {
      margin-right: 5px;
    }
     :deep(.el-input__inner) {
      background-color: rgb(48, 48, 48);
      color: #409eff;
    }
  }
  .item-name {
    width: 140px;
    padding-left: 15px;
  }
}
</style>
