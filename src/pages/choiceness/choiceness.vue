<template>
  <view>
    <view>
      <uni-swiper-dot
        @clickItem="clickItem"
        :info="info"
        :current="current"
        :mode="mode"
        :dots-styles="dotsStyles"
        field="content"
      >
        <swiper class="swiper-box" @change="change">
          <swiper-item v-for="(item, index) in info" :key="index">
            <view  class="swiper-item">
              <image
                class="image"
                :src="item.url"
                mode="aspectFill"
                :draggable="false"
              />
              <view
                style="
                  background-color: rgba(0, 0, 0, 0.3);
                  bottom: 0px;
                  position: absolute;
                  left: 0px;
                  right: 0px;
                "
                ><text>{{ item.content }}</text></view
              >
            </view>
          </swiper-item>
        </swiper>
      </uni-swiper-dot>
    </view>
    <view class="middle">
      <uni-grid-item v-for="(item, index) in 3" :index="index" :key="index">
					<view class="grid-item-box" style="background-color: #fff;">
						<uni-icons type="image" :size="30" color="#777" />
						<text class="text">文本信息</text>
					</view>
				</uni-grid-item>
    </view>
  </view>
</template>
  
  <script>
export default {
  data() {
    return {
      info: [
        {
          url: "https://web-assets.dcloud.net.cn/unidoc/zh/shuijiao.jpg",
          content: "内容 A",
        },
        {
          url: "https://web-assets.dcloud.net.cn/unidoc/zh/shuijiao.jpg",
          content: "内容 B",
        },
        {
          url: "https://web-assets.dcloud.net.cn/unidoc/zh/shuijiao.jpg",
          content: "内容 C",
        },
      ],
      gridList: [
        {
          icon: 'https://img.yzcdn.cn/vant/user-active.png',
          text: '我的订单'
        },
        {
          icon: 'https://img.yzcdn.cn/vant/user-inactive.png',
          text: '我的收藏'
        },
        {
          icon: 'https://img.yzcdn.cn/vant/user-inactive.png',
          text: '我的地址'
        },
        {
          icon: 'https://img.yzcdn.cn/vant/user-inactive.png',
          text: '我的优惠券'
        },
        {
          icon: 'https://img.yzcdn.cn/vant/user-inactive.png',
          text: '联系客服'
        },
        {
          icon: 'https://img.yzcdn.cn/vant/user-inactive.png',
          text: '关于我们'
        }
      ],
      current: 0,
      mode: "nav",
    };
  },
  onLoad() {},
  methods: {
    change(e) {
      this.current = e.detail.current;
    },
    clickItem(e) {
      this.swiperDotIndex = e;
    },
  },
};
</script>
  
  <style>
.swiper-box {
  height: 200px;
}
.swiper-item {
  display: flex;
  flex-direction: column;
  justify-content: center;
  height: 200px;
  color: #ffffff;
  background-color: #606162;
}
.image {
  width: 100vw;
}
@media screen and (min-width: 500px) {
  .uni-swiper-dot-box {
    width: 300px;
    margin: 0 auto;
    margin-top: 8px;
  }

  .image {
    width: 100%;
  }
  .middle{
    width: 100%;
    height: 500px;
  }
}
</style>
  