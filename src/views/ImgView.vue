<template>
      <el-carousel :interval="4000" type="card" height="400px">
    <el-carousel-item v-for="item in 6" :key="item" name="abcc" label="123">
      <el-image src="/b7dd1f88660effcb0d4d0552c67602c51665979154892.png" fit="scale-down"
        :preview-src-list="['/b7dd1f88660effcb0d4d0552c67602c51665979154892.png']" />
    </el-carousel-item>
  </el-carousel>
</template>