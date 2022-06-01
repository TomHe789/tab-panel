<template>
  <div class="color-picker">
    <span>background</span>
    <el-color-picker v-model="color" />
    <span class="color-value">{{ formattColorStr(color) }}</span>
  </div>
</template>

<script setup>
import { ref } from 'vue'

defineProps({
  color: String,
})

const formattColorStr = str => {
  let reg = /^#([0-9A-Fa-f]{3}|[0-9A-Fa-f]{6})$/
  if (!reg.test(str)) {
    return
  }
  let newStr = str.toLowerCase().replace(/\#/g, '')
  let len = newStr.length
  if (len == 3) {
    let t = ''
    for (var i = 0; i < len; i++) {
      t += newStr.slice(i, i + 1).concat(newStr.slice(i, i + 1))
    }
    newStr = t
  }
  let arr = [] //将字符串分隔，两个两个的分隔
  for (let i = 0; i < 6; i = i + 2) {
    let s = newStr.slice(i, i + 2)
    arr.push(parseInt('0x' + s))
  }
  return 'rgb(' + arr.join(',') + ')'
}
</script>

<style lang="less" scoped>
.color-picker {
  border-bottom: 1px solid rgba(255, 255, 255, 0.4);
  padding-left: 15px;
  position: relative;
  display: flex;
  align-items: center;
  span {
    margin-right: 17px;
  }
  .color-value {
    position: absolute;
    left: 180px;
    top: 8px;
  }
}
/deep/ .el-color-picker__trigger {
  border: none;
  width: 230px;
  .el-color-picker__color {
    border-radius: 0;
    .el-icon {
      display: none;
    }
  }
}
</style>
