<script setup lang="ts">
import { ElMenu, ElMenuItem, ElSubMenu, ElCarousel, ElCarouselItem, ElImage } from 'element-plus';
import { h, reactive, ref } from 'vue'
import ImgView from './ImgView.vue'
import HelloView from './HelloView.vue'

const activeIndex = ref('1')
const handleSelect = (key: string, keyPath: string[]) => {
  console.log(key, keyPath)
}
const currentView = ref('ImgView')
const components = {
  ImgView,
  HelloView
}
const flag = ref(true)
const switchCom = () => {
  flag.value = !flag.value
  if (flag.value) currentView.value = "HelloView";
  else currentView.value = "ImgView"
}
</script>

<template>

  <el-menu :default-active="activeIndex" class="el-menu-demo" mode="horizontal" @select="handleSelect">
    <el-menu-item index="1">Processing Center</el-menu-item>
    <el-sub-menu index="2">
      <template #title>Workspace</template>
      <el-menu-item index="2-1">item one</el-menu-item>
      <el-menu-item index="2-2">item two</el-menu-item>
      <el-menu-item index="2-3">item three</el-menu-item>
      <el-sub-menu index="2-4">
        <template #title>item four</template>
        <el-menu-item index="2-4-1">item one</el-menu-item>
        <el-menu-item index="2-4-2">item two</el-menu-item>
        <el-menu-item index="2-4-3">item three</el-menu-item>
      </el-sub-menu>
    </el-sub-menu>
    <el-menu-item index="3">Info</el-menu-item>
    <el-menu-item index="4">Orders</el-menu-item>
  </el-menu>
  <div class="h-6" />
  <el-button type="primary" @click="switchCom">aaa</el-button>
  <component :is="components[currentView]"></component>
</template>

<style scoped>
.el-carousel__item h3 {
  color: #475669;
  opacity: 0.75;
  line-height: 200px;
  margin: 0;
  text-align: center;
}

.el-carousel__item:nth-child(2n) {
  background-color: #99a9bf;
}

.el-carousel__item:nth-child(2n + 1) {
  background-color: #d3dce6;
}
</style>

