<template>
  <div class="left-panel">
    <el-menu default-active="2" @select="handleSelect">
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
    <sene-configuration v-show="selectIndex == 2" />
    <!-- 控制配置 -->
    <control-configuration v-show="selectIndex == 3" />
    <!-- 环境光 -->
    <enviroment-light v-show="selectIndex == 4" />
    <light-front v-show="selectIndex == 4" />
    <!-- 材质选择 -->
    <material-select v-show="selectIndex == 5" />
    <!-- 模型参数 -->
    <model-parameter v-show="selectIndex == 6" />
  </div>
</template>

<script setup>
import { ref, onMounted, provide, computed, reactive } from 'vue'
import { Setting } from '@element-plus/icons-vue'
import axios from 'axios'
import SeneConfiguration from './../panel/SceneConfiguration.vue'
import ModelParameter from './../panel/ModelParameter.vue'
import EnviromentLight from './../panel/EnviromentLight.vue'
import LightFront from './../panel/LightFront.vue'
import ControlConfiguration from './../panel/ControlConfiguration.vue'
import MaterialSelect from '../panel/MaterialSelect.vue'

const selectIndex = ref(2)
const result = ref(null)

const handleSelect = (key, keyPath) => {
  console.log(key)
  selectIndex.value = key
}

// provide('panelData', result)

// 读取本地json数据
// axios.get('/dataSource/panelData.json').then(res => {
//   if (res.status === 200) {
//     result.value = res.data
//   }
// })
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
    &:hover,
    &:focus {
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
  width: 350px;
  height: 100vh;
  padding-top: 75px;
  position: fixed;
  right: 0;
  top: 0;
  background-color: rgb(85, 92, 100);
}
</style>
