<template>
  <view class="work-container">
    <!-- 轮播图 -->
    <!-- <uni-swiper-dot class="uni-swiper-dot-box" :info="data" :current="current" field="content">
      <swiper class="swiper-box" :current="swiperDotIndex" @change="changeSwiper">
        <swiper-item v-for="(item, index) in data" :key="index">
          <view class="swiper-item" @click="clickBannerItem(item)">
            <image :src="item.image" mode="aspectFill" :draggable="false" />
          </view>
        </swiper-item>
      </swiper>
    </uni-swiper-dot> -->

    <!-- 宫格组件 -->
    <!-- <uni-section title="填报链接" type="line"></uni-section> -->
	<uni-forms ref="valiForm" :rules="rules" :model="valiFormData" :label-position='top' labelWidth="80px">
		<uni-forms-item label="填报链接" required name="name">
			<uni-easyinput v-model="valiFormData.name" placeholder="请输入填报链接" />
		</uni-forms-item>
	</uni-forms>
	<uni-section title="上传截图" type="line"></uni-section>
	<view class="example-body">
		<uni-file-picker limit="9" title="最多选择9张图片" :source-type="sourceType"></uni-file-picker>
	</view>
	<!-- <uni-section title="发布内容" type="line"></uni-section> -->
	<uni-forms ref="valiForm" :rules="rules" :model="valiFormData" :label-position='top' labelWidth="80px">
		<uni-forms-item label="发布内容" required name="name">
			<uni-easyinput v-model="valiFormData.name" placeholder="请输入发布内容" />
		</uni-forms-item>
	</uni-forms>
	<!-- <uni-section title="发布平台" type="line"></uni-section> -->
	<uni-forms ref="valiForm" :rules="rules" :model="valiFormData" :label-position='top' labelWidth="80px">
		<uni-forms-item label="发布平台" required name="name">
			<uni-easyinput v-model="valiFormData.name" placeholder="请输入发布平台" />
		</uni-forms-item>
	</uni-forms>
	<!-- <uni-section title="发布时间" type="line"></uni-section> -->
	<uni-forms ref="valiForm" :rules="rules" :model="valiFormData" :label-position='top' labelWidth="80px">
		<uni-forms-item label="发布时间" required name="name">
			<uni-easyinput v-model="valiFormData.name" placeholder="请输入发布时间" />
		</uni-forms-item>
	</uni-forms>
	<button type="primary" @click="submit('valiForm')">提交</button>
    <!-- <view class="grid-body">
      <uni-grid :column="4" :showBorder="false" @change="changeGrid">
        <uni-grid-item>
          <view class="grid-item-box">
            <uni-icons type="person-filled" size="30"></uni-icons>
            <text class="text">用户管理</text>
          </view>
        </uni-grid-item>
        <uni-grid-item>
          <view class="grid-item-box">
            <uni-icons type="staff-filled" size="30"></uni-icons>
            <text class="text">角色管理</text>
          </view>
        </uni-grid-item>
        <uni-grid-item>
          <view class="grid-item-box">
            <uni-icons type="color" size="30"></uni-icons>
            <text class="text">菜单管理</text>
          </view>
        </uni-grid-item>
        <uni-grid-item>
          <view class="grid-item-box">
            <uni-icons type="settings-filled" size="30"></uni-icons>
            <text class="text">部门管理</text>
          </view>
        </uni-grid-item>
        <uni-grid-item>
          <view class="grid-item-box">
            <uni-icons type="heart-filled" size="30"></uni-icons>
            <text class="text">岗位管理</text>
          </view>
        </uni-grid-item>
        <uni-grid-item>
          <view class="grid-item-box">
            <uni-icons type="bars" size="30"></uni-icons>
            <text class="text">字典管理</text>
          </view>
        </uni-grid-item>
        <uni-grid-item>
          <view class="grid-item-box">
            <uni-icons type="gear-filled" size="30"></uni-icons>
            <text class="text">参数设置</text>
          </view>
        </uni-grid-item>
        <uni-grid-item>
          <view class="grid-item-box">
            <uni-icons type="chat-filled" size="30"></uni-icons>
            <text class="text">通知公告</text>
          </view>
        </uni-grid-item>
        <uni-grid-item>
          <view class="grid-item-box">
            <uni-icons type="wallet-filled" size="30"></uni-icons>
            <text class="text">日志管理</text>
          </view>
        </uni-grid-item>
      </uni-grid>
    </view> -->
  </view>
</template>

<script>
  export default {
    data() {
      return {
        current: 0,
        swiperDotIndex: 0,
        // 校验表单数据
        valiFormData: {
        	name: '',
        	age: '',
        	introduction: '',
        },
      }
    },
    methods: {
      clickBannerItem(item) {
        console.info(item)
      },
      changeSwiper(e) {
        this.current = e.detail.current
      },
      changeGrid(e) {
        this.$modal.showToast('模块建设中~')
      }
    }
  }
</script>

<style lang="scss">
	.example-body {
		padding: 10px;
		padding-top: 0;
	}
	.example {
		padding: 15px;
		background-color: #fff;
	}
  /* #ifndef APP-NVUE */
  page {
    display: flex;
    flex-direction: column;
    box-sizing: border-box;
    background-color: #fff;
    min-height: 100%;
    height: auto;
  }

  view {
    font-size: 14px;
    line-height: inherit;
  }

  /* #endif */

  .text {
    text-align: center;
    font-size: 26rpx;
    margin-top: 10rpx;
  }

  .grid-item-box {
    flex: 1;
    /* #ifndef APP-NVUE */
    display: flex;
    /* #endif */
    flex-direction: column;
    align-items: center;
    justify-content: center;
    padding: 15px 0;
  }

  .uni-margin-wrap {
    width: 690rpx;
    width: 100%;
    ;
  }

  .swiper {
    height: 300rpx;
  }

  .swiper-box {
    height: 150px;
  }

  .swiper-item {
    /* #ifndef APP-NVUE */
    display: flex;
    /* #endif */
    flex-direction: column;
    justify-content: center;
    align-items: center;
    color: #fff;
    height: 300rpx;
    line-height: 300rpx;
  }

  @media screen and (min-width: 500px) {
    .uni-swiper-dot-box {
      width: 400px;
      /* #ifndef APP-NVUE */
      margin: 0 auto;
      /* #endif */
      margin-top: 8px;
    }

    .image {
      width: 100%;
    }
  }
</style>
