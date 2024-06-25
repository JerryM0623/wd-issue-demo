<!-- 使用 type="home" 属性设置首页，其他页面不需要设置，默认为page；推荐使用json5，更强大，且允许注释 -->
<route lang="json5" type="home">
{
  style: {
    navigationStyle: 'custom',
    navigationBarTitleText: '首页',
  },
}
</route>
<template>
  <wd-form ref="form" :model="formModel">
    <wd-cell-group border>
      <wd-input
        type="text"
        label="功德芳名"
        label-width="100px"
        clearable
        v-model="formModel.name"
        placeholder="请输入用户名"
      />
      <wd-input
        type="digit"
        label="手机号码"
        label-width="100px"
        clearable
        v-model="formModel.tel"
        placeholder="请输入手机号码"
        :maxlength="11"
      />
      <wd-textarea
        label="个人祈愿"
        label-width="100px"
        v-model="formModel.wish"
        :maxlength="30"
        clearable
        show-word-limit
        center
        placeholder="请输入个人祈愿"
        style="height: 200rpx"
      />
    </wd-cell-group>
    <view class="footer">
      <wd-button custom-class="submit-button" :round="false" @click="handleSubmit" block>
        提交
      </wd-button>
    </view>
  </wd-form>
</template>

<script lang="ts" setup>
const formModel = reactive({
  name: '',
  tel: '',
  wish: '保佑我全家身体健康，万事如意！',
})
const handleSubmit = () => {
  console.log('submit')
}
</script>

<style>
.submit-button {
  background: #b8741a !important;
}
</style>
