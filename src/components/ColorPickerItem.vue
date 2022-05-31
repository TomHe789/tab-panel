<template>
  <div class="color-picker">
    <span>background</span>
    <el-color-picker v-model="color" />
  </div>
</template>

<script setup>
import { ref } from 'vue'
defineProps({
  color: String,
})
</script>

<style lang="less" scoped>
.color-picker {
  border-bottom: 1px solid rgba(255, 255, 255, 0.4);
  padding-left: 15px;
  span{
    margin-right: 17px;
  }
}
/deep/ .el-color-picker__trigger {
  border: none;
  width: 200px;
  .el-color-picker__color {
    border-radius: 0;
  }
}
</style>
