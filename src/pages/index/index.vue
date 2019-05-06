<template>
  <div>
    <!-- 搜索 -->
    <div class="search">
      <!-- 搜索框 -->
      <div class="input-box"
           placeholder="请输入商品">
        <input type="text">
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
      <swiper-item>
        <navigator url="">
          <image src="/static/uploads/banner1.png">
          </image>
        </navigator>
      </swiper-item>
      <swiper-item>
        <navigator url="">
          <image src="/static/uploads/banner2.png">
          </image>
        </navigator>
      </swiper-item>
      <swiper-item>
        <navigator url="">
          <image src="/static/uploads/banner3.png">
          </image>
        </navigator>
      </swiper-item>
    </swiper>
    <!-- 导航 -->
    <div class="navs">
      <navigator url="">
        <image src="/static/uploads/icon_index_nav_1@2x.png">
        </image>
      </navigator>
      <navigator url="">
        <image src="/static/uploads/icon_index_nav_2@2x.png">
        </image>
      </navigator>
      <navigator url="">
        <image src="/static/uploads/icon_index_nav_3@2x.png">
        </image>
      </navigator>
      <navigator url="">
        <image src="/static/uploads/icon_index_nav_4@2x.png">
        </image>
      </navigator>
    </div>
    <!-- 楼层 -->
    <div class="floors">
      <div class="floor">
        <div class="title">
          <image src="/static/uploads/pic_floor02_title.png">
          </image>
        </div>
        <div class="pics">
          <navigator url="">
            <image src="/static/uploads/pic_floor02_1@2x.png">
            </image>
          </navigator>
          <navigator url="">
            <image src="/static/uploads/pic_floor02_2@2x.png">
            </image>
          </navigator>
          <navigator url="">
            <image src="/static/uploads/pic_floor02_3@2x.png">
            </image>
          </navigator>
          <navigator url="">
            <image src="/static/uploads/pic_floor02_4@2x.png">
            </image>
          </navigator>
          <navigator url="">
            <image src="/static/uploads/pic_floor02_5@2x.png">
            </image>
          </navigator>
        </div>
      </div>
      <div class="floor">
        <div class="title">
          <image src="/static/uploads/pic_floor02_title.png">
          </image>
        </div>
        <div class="pics">
          <navigator url="">
            <image src="/static/uploads/pic_floor02_1@2x.png">
            </image>
          </navigator>
          <navigator url="">
            <image src="/static/uploads/pic_floor02_2@2x.png">
            </image>
          </navigator>
          <navigator url="">
            <image src="/static/uploads/pic_floor02_3@2x.png">
            </image>
          </navigator>
          <navigator url="">
            <image src="/static/uploads/pic_floor02_4@2x.png">
            </image>
          </navigator>
          <navigator url="">
            <image src="/static/uploads/pic_floor02_5@2x.png">
            </image>
          </navigator>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {

}
</script>

<style scoped>
/* 搜索 */
.search {
}
.search .input-box {
  background-color: #ee4451;
  padding: 20rpx 30rpx;
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
  padding-top: 30rpx;
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
