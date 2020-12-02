<template>
  <view class="message">
    <uni-search-bar
      @confirm="comfirm1"
      @input="change"
      v-model="searchValue"
    />
    <view class="messageList">
      <uni-list>
        <uni-list-item
          title="列表左侧带略缩图"
          note="列表描述信息"
          thumb="https://img-cdn-qiniu.dcloud.net.cn/new-page/uni.png"
          thumb-size="lg"
          rightText="右侧文字"
        ></uni-list-item>
      </uni-list>
    </view>
  </view>
</template>

<script>
export default {
  data() {
    return {
      searchValue: {},
    };
  },
  methods: {
    // enter 触发
    comfirm1() {
      console.log(this.searchValue.value, "search");
    },
    // 值变化触发
    change() {
      console.log(this.searchValue.value);
    },
  },
};
</script>

<style lang="less">
.message {
  width: 100%;
  .messageList {
    width: 95%;
    margin: 0 auto;
  }
}
</style>
