<template>
  <div>
    <!-- 搜索 -->
    <div class="search">
      <!-- 搜索框 -->
      <div class="input-box">
        <input type="text"
               placeholder="请输入商品">
      </div>
      <!-- 搜索结果 -->
      <div class="result"></div>
    </div>
    <!-- 焦点图 -->
    <swiper class="banner"
            indicator-dots
            autoplay
            circular
            indicator-color="rgba(255,255,255,.6)"
            indicator-active-color="#fff">
      <swiper-item v-for="(list,key) in bannerList"
                   :key="key">
        <navigator :url="list.navigator_url">
          <image :src="list.image_src">
          </image>
        </navigator>
      </swiper-item>
    </swiper>
    <!-- 导航 -->
    <div class="navs">
      <navigator :url="list.navigator_url"
                 v-for="(list,key) in navList"
                 :key="key">
        <image :src="list.image_src">
        </image>
      </navigator>
    </div>
    <!-- 楼层 -->
    <div class="floors">
      <div class="floor"
           v-for="(list , key) in floorList"
           :key="key">
        <div class="title">
          <image :src="list.floor_title.image_src">
          </image>
        </div>
        <div class="pics">
          <navigator :url="item.navigator_url"
                     v-for="(item,index) in list.product_list"
                     :key="index">
            <image :src="item.image_src">
            </image>
          </navigator>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
// 导入 Promise 模块
import request from '@/utils/request.js'
export default {
  data () {
    return {
      bannerList: [],
      navList: [],
      floorList: []
    }
  },

  methods: {
    //焦点图接口
    async getBanner () {
      //！！！传统异步
      // var _this = this
      // mpvue.request({
      //   url: 'https://www.zhengzhicheng.cn/api/public/v1/home/swiperdata',
      //   success: function (info) {
      //     // console.log(info)
      //     _this.bannerList = info.data.message
      //   }
      // })
      let { message } = await request({ url: '/api/public/v1/home/swiperdata' })
      this.bannerList = message

    },
    //导航接口
    async getNavs () {
      //！！！传统异步
      // var _this = this
      // mpvue.request({
      //   url: 'https://www.zhengzhicheng.cn/api/public/v1/home/catitems',
      //   success: function (info) {
      //     // console.log(info)
      //     _this.navList = info.data.message
      //   }
      // })
      let { message } = await request({
        url: '/api/public/v1/home/catitems'
      })
      this.navList = message
    },
    //楼层接口
    async getFloors () {
      let { message } = await request({
        url: '/api/public/v1/home/floordata'
      })
      console.log(message)
      this.floorList = message
    }
  },

  mounted () {
    console.log('发起请求')
    this.getBanner()
    this.getNavs()
    this.getFloors()
  }
}
</script>

<style scoped lang = "less">
/* 在 vue 中使用less需要安装 */
/* less-loader、less 并且要配置 */
/* 在mpvue只需安装，无需配置 */

/* 搜索 */
.search {
}
.search {
  .input-box {
    background-color: #ee4451;
    padding: 20rpx 30rpx;
  }
}
.search .input-box input {
  height: 75rpx;
  background-color: #fff;
  border-radius: 10rpx;
  padding-left: 15rpx;
  font-size: 27rpx;
  color: #666;
}

/* 焦点图 */
.banner {
  width: 750rpx;
  height: 340rpx;
}
.banner navigator {
  width: 100%;
  height: 100%;
}

/* 导航 */
.navs {
  display: flex;
  justify-content: space-around;
  padding: 20rpx 0;
}
.navs navigator {
  width: 128rpx;
  height: 140rpx;
}

/* 楼层 */
.floors {
}
.floors .title {
  width: 750rpx;
  height: 59rpx;
  padding-top: 30rpx;
  padding-left: 15rpx;
  background: #f4f4f4;
}
.floors .pics {
  padding: 20rpx 18rpx;
  overflow: hidden;
}
.floors .pics navigator {
  height: 188rpx;
  margin-left: 10rpx;
  margin-bottom: 10rpx;
  float: left;
}
.floors .pics navigator:first-child {
  width: 232rpx;
  height: 386rpx;
  margin-left: 0;
}
.floors .pics navigator:nth-child(2) {
  width: 273rpx;
}
.floors .pics navigator:nth-child(3) {
  width: 193rpx;
}
.floors .pics navigator:nth-child(4) {
  width: 193rpx;
}
.floors .pics navigator:last-child {
  width: 273rpx;
}
</style>
