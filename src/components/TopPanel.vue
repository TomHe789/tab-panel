<template>
  <div class="top-container">
    <el-button type="primary">保存</el-button>
    <el-button type="primary">清空</el-button>
  </div>
</template>

<script setup>
import { ref } from 'vue'
</script>

<style lang="less" scoped>
.top-container {
  width: 100vw;
  height: 55px;
  position: fixed;
  top: 0;
  left: 0;
  background-color: rgba(179, 192, 209, 0.4);
  z-index: 9;
  .el-button {
    position: absolute;
    right: 30px;
    top: 16px;
    width: 80px;
    border-radius: 8px;
    &:last-of-type {
      right: 140px;
    }
  }
}
</style>
