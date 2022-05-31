<template>
  <div class="panel-item">
    <div class="panel-top">
      <div
        :class="['arrow', show ? 'arrow-bottom' : 'arrow-right'].join(' ')"
        @click="show = !show"
      ></div>
      <span class="panel-title">{{ panelTitle }}</span>
    </div>
    <el-collapse-transition>
      <div v-show="show">
        <div class="panel-bottom">
          <slot name="panelBottom"></slot>
        </div>
      </div>
    </el-collapse-transition>
  </div>
</template>

<script setup>
import { ref } from 'vue'

defineProps({
  panelTitle: String,
})

const show = ref(true)
</script>

<style lang="less" scoped>
.panel-item {
  color: #fff;
  font-size: 14px;
  font-weight: 300;
  .panel-top {
    height: 30px;
    line-height: 30px;
    border-bottom: 1px solid rgba(255, 255, 255, 0.4);
    .panel-title {
      margin-left: 10px;
    }
  }
  .panel-bottom {
    border-left: 5px rgb(243, 226, 200) solid;
  }
}
.arrow {
  width: 0;
  height: 0;
  border-width: 6px;
  border-style: solid;
  border-color: transparent;
  position: relative;
  left: 5px;
  display: inline-block;
}
.arrow-bottom {
  border-top-color: #fff;
  top: 4px;
}
.arrow-right {
  border-left-color: #fff;
  top: 0px;
  left: 8px;
}
</style>
