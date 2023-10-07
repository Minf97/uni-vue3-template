<script setup lang="ts">
import { useTitle } from '@/hooks/useTitle';
import { forward } from '@/utils/router';

const { title, changeTitle } = useTitle();
function goTest() {
  forward('test', {
    a: 1
  });
}

const demo = () => {
  console.log(123);

}
</script>

<template>
  <view class="content">
    <image class="logo" src="/static/logo.png" />
    <view class="text-area">
      <text class="title">{{ title }}</text>
    </view>
    <view @click="changeTitle">changeTitle</view>
    <view @click="goTest">测试页</view>
    <u-button @click="demo" type="primary" text="月落"></u-button>
    <button hover-class="hover1" class="demo1">测试按钮</button>
  </view>
</template>

<style scoped lang="scss">
.demo1 {
  background-color: pink;
}
.hover1 {
  background-color: green !important;
}
.content {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}
.logo {
  margin-left: auto;
  margin-right: auto;
  margin-top: 200rpx;
  margin-bottom: 50rpx;
  width: 200rpx;
  height: 200rpx;
}
.text-area {
  display: flex;
  justify-content: center;
}
.title {
  font-size: 36rpx;
  color: #8f8f94;
}
</style>
