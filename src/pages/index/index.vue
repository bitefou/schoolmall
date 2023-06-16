<template>
  <view>
    <view>
      <swiper
        class="swiper_box"
        v-on:change="swiperchange"
        indicator-dots="true"
        indicator-active-color="#fff"
      >
        <swiper-item wx:key="id">
          <image
            mode="aspectFill"
            @click="imgClick"
            src="https://dcdn.it120.cc/2020/01/07/c3183558-55e8-4589-9ea7-81670004941a.jpg"
          />
        </swiper-item>
        <swiper-item>
          <image
            mode="aspectFill"
            @click="imgClick"
            src="https://dcdn.it120.cc/2020/01/07/b7471e4f-dc0d-4245-afb7-b64fbd9bb29a.jpg"
          />
        </swiper-item>
        <swiper-item>
          <image
            mode="aspectFill"
            @click="imgClick"
            src="https://dcdn.it120.cc/2020/01/07/5425289c-fb82-4ab4-a193-933ddba71496.jpg"
          />
        </swiper-item>
      </swiper>
    </view>
    <view class="btn">
      <button
        v-if="swiperCurrent+1==swiperMaxNumber"
        @click="goToIndex" type="primary" size="mini"
      >
        进入店铺
      </button>
    </view>
  </view>
</template>

<script>
export default {
  data() {
    return {
      banners: [],
      swiperMaxNumber: 0,
      swiperCurrent: 0,
    };
  },
  onLoad() {
  },
  methods: {
	//图片点击提示往左滑,当为最后一张照片时不提示
    imgClick() {
      if (this.swiperCurrent + 1 != this.swiperMaxNumber) {
        uni.showToast({
          title: "左滑进入",
          icon: "none",
          duration:2000
        });
      }
    },
	//左滑加1
	swiperchange: function (e) {
		this.swiperCurrent= e.detail.current,
        this.swiperMaxNumber=3
  },
  //滑完显示进入按钮
  goToIndex() {
    uni.switchTab({
      url: "/pages/choiceness/choiceness",
    });
  },
  },
};
</script>

<style>
.swiper_box {
  width: 100vw;
  height: 100vh;
  position: absolute;
}
swiper-item {
  width: 100vw;
  height: 100vh;
  position: absolute;
}
image {
  width: 100vw;
  height: 100vh;
  position: absolute;
}
.btn {
  position: absolute;
  left: 0;
  right: 0;
  bottom: 50rpx;
  display: flex;
  justify-content: center;
}
</style>
