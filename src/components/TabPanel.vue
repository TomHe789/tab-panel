<template>
  <div class="left-panel">
    <el-menu default-active="1" @select="handleSelect">
      <el-menu-item index="1">
        <el-icon><Setting /></el-icon>
        <span>配置参数</span>
      </el-menu-item>
      <el-menu-item index="2">
        <el-icon><Setting /></el-icon>
        <span>场景配置</span>
      </el-menu-item>
      <el-menu-item index="3">
        <el-icon><Setting /></el-icon>
        <span>控制配置</span>
      </el-menu-item>
      <el-menu-item index="4">
        <el-icon><Setting /></el-icon>
        <span>环境光</span>
      </el-menu-item>
      <el-menu-item index="5">
        <el-icon><Setting /></el-icon>
        <span>材质选择</span>
      </el-menu-item>
      <el-menu-item index="6">
        <el-icon><Setting /></el-icon>
        <span>模型参数</span>
      </el-menu-item>
    </el-menu>
  </div>
  <div class="right-panel">
    <!-- 场景配置 -->
    <sene-configuration />
    <!-- 控制配置 -->
    <control-configuration />
    <!-- 环境光 -->
    <enviroment-light />
    <!-- 模型参数 -->
    <model-parameter />
  </div>
</template>

<script setup>
import { ref } from 'vue'
import { Setting } from '@element-plus/icons-vue'
import SeneConfiguration from './SceneConfiguration.vue'
import ModelParameter from './ModelParameter.vue'
import EnviromentLight from './EnviromentLight.vue'
import ControlConfiguration from './ControlConfiguration.vue'

defineProps({
  msg: String,
})

const count = ref(0)

const handleSelect = (key, keyPath) => {
  console.log(key, keyPath)
}
</script>

<style lang="less" scoped>
.left-panel {
  .el-menu {
    width: 150px;
    height: 100vh;
    background-color: rgb(85, 92, 100);
  }
  .el-menu-item {
    transition: none;
    &:hover {
      background-color: rgb(149, 161, 177);
    }
  }
  .el-menu-item {
    color: rgba(255, 255, 255, 0.8);
  }
  .el-menu-item.is-active {
    color: rgba(255, 255, 255, 1);
  }
}
.right-panel {
  width: 300px;
  height: 100vh;
  position: fixed;
  right: 0;
  top: 0;
  background-color: rgb(85, 92, 100);
}
</style>
