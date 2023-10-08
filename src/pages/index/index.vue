<script setup lang="ts">
import { useTitle } from '@/hooks/useTitle';
import { forward } from '@/utils/router';

const { title, changeTitle } = useTitle();
function goTest() {
  forward('test', {
    a: 1
  });
}

const options = ref([{
  text: '综合推荐',
  value: 1,
  checked: true
}, {
  text: '新品优先',
  value: 2
}, {
  text: '评论数从高到低',
  value: 3
}]);
const range = ref("总和推荐");
const rangeShow = ref(false);
const ddmRange = ref(null);

const filterTap = () => {
  //显示下拉框
  ddmRange.value.show()
  rangeShow.value = true;
};

const rangeItemClick = (e) => {
  console.log(e)
  range.value = e.text
  rangeClose()
};

const rangeClose = () => {
  rangeShow.value = false;
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
}</style>
