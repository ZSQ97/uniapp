<template>
  <view class="container">
    <uni-search-bar
      @confirm="comfirm1"
      @input="change"
      v-model="searchValue"
    />
    <carousel
      :img-list="img"
      url-key="url"
      @selected="selectedBanner"
    />

    <scroll-view scroll-x="true">
      <view class="Ind_select">
        <view
          class="box"
          @click="goDetail(2)"
        >
          <image
            src="../../static/slide1.jpg"
            mode=""
          ></image>
          <view class="span">
            图片采集
          </view>
        </view>
        <view class="box">
          <image
            src="../../static/slide2.jpg"
            mode=""
          ></image>
          <view class="span">
            数据录入
          </view>
        </view>
        <view class="box">
          <image
            src="../../static/slide3.jpg"
            mode=""
          ></image>
          <view class="span">
            审批
          </view>
        </view>
        <view class="box">
          <image
            src="../../static/slide4.jpg"
            mode=""
          ></image>
          <view class="span">
            你猜
          </view>
        </view>
      </view>
    </scroll-view>
    <scroll-view scroll-y="true">
      <view class="news">
        <view class="news_top"><text>焊联推送</text></view>
        <view class="news_middle">
          <uni-list>
            <uni-list-item
              title="列表文字"
              note="列表文字"
              clickable
              @click="goDetail(1)"
            ></uni-list-item>
            <!-- <uni-list-item
              :disabled="true"
              title="列表文字"
              note="列表禁用状态"
            ></uni-list-item> -->
            <uni-list-item
              v-for="item in news"
              :key="item.id"
              :title="item.title"
              :note="item.text"
              :thumb="item.url"
              thumb-size="lg"
              :rightText="'阅读次数 '+item.num"
              clickable
              @click="goDetail(item)"
            ></uni-list-item>
            <!-- <uni-list-item :show-extra-icon="true" :extra-icon="extraIcon1" title="列表左侧带扩展图标" ></uni-list-item> -->
          </uni-list>
        </view>
      </view>
    </scroll-view>
  </view>

</template>

<script>
import carousel from "../../components/vear-carousel/vear-carousel.vue";
export default {
  components: {
    carousel,
  },
  data() {
    return {
      href: "https://uniapp.dcloud.io/component/README?id=uniui",
      searchValue: {},
      img: [
        { url: "../../static/save1.jpg" },
        { url: "../../static/save2.jpg" },
        { url: "../../static/save3.jpg" },
        { url: "../../static/01s.jpg" },
        { url: "../../static/02s.jpg" },
        { url: "../../static/shuijiao.jpg" },
      ],
      news: [
        {
          id: 1,
          url: "../../static/shuijiao.jpg",
          title: "hello world",
          text: "有没有这样一首歌会让你轻轻跟着喝...",
          num: "23",
        },
        {
          id: 2,
          url: "../../static/02s.jpg",
          title: "hello world",
          text: "有没有这样一首歌会让你轻轻跟着喝...",
          num: "233",
        },
        {
          id: 3,
          url: "../../static/shuijiao.jpg",
          title: "hello world",
          text: "有没有这样一首歌会让你轻轻跟着喝...",
          num: "121",
        },
      ],
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
    selectedBanner(item, index) {
      console.log("🥒", item, index);
    },
    goDetail(item) {
      // uni.navigateTo({
      //   url: "../tabBar/component/component",
      // });
      console.log(item);
    },
  },
};
</script>

<style lang="less">
.container {
  padding: 0px 0 50px 0;
  font-size: 14px;
  line-height: 24px;
  // background: #007AFF;
  /* display: flex; */
  .uni-searchbar {
    padding: 8px 8px 0;
  }
  .Ind_select {
    width: 1000upx;
    // background: #CCCCCC;
    height: 108upx;
    overflow-x: auto;
    padding: 10upx 0;
    display: flex;
    .box {
      width: 214upx;
      height: 108upx;
      // background: red;
      margin: 0 20upx;
      position: relative;
      image {
        width: 100%;
        height: 108upx;
        opacity: 0.8;
      }
      .span {
        width: 100%;
        height: 100%;
        // background: red;
        color: #fff;
        font-size: 16px;
        line-height: 108upx;
        text-align: center;
        position: absolute;
        top: 0;
      }
    }
  }
  .news {
    min-height: 500upx;
    
		box-shadow: 0 1px 2px #F0F0F0;
    width: 95%;
    margin: 0 auto;
    .news_top {
      text-align: center;
      line-height: 90upx;
      height: 90upx;
      background: #e6e6e6;
      // opacity: ;
      color: rgb(13, 45, 79);
      font-size: 16px;
    }
  }
}
</style>
