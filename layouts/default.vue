<template>
  <div class="container">
    <el-container>
      <el-container>
        <el-header>
          <div>
            <ul>
              <li>
                <nuxt-link :to="{name:'index'}">HOME</nuxt-link>
              </li>
              <li>
                <nuxt-link :to="{name:'about'}">ABOUT</nuxt-link>
              </li>
              <li>
                <nuxt-link :to="{name:'news',params:{newid:123}}">NEWS</nuxt-link>
              </li>
              <li>
                <nuxt-link :to="{name:'list'}">List</nuxt-link>
              </li>
            </ul>
          </div>
        </el-header>
        <div class="slide">
          <div v-swiper:mySwiper="swiperOption">
          <div class="swiper-wrapper">
            <div class="swiper-slide">
              <img src="~assets/images/1.jpg">
            </div>
            <div class="swiper-slide">
              <img src="~assets/images/2.jpg">
            </div>
            <div class="swiper-slide">
              <img src="~assets/images/3.jpg">
            </div>
          </div>
          <!-- <div class="swiper-pagination swiper-pagination-bullets"></div> -->
        </div>
        </div>
        <el-main>
          <nuxt/>
        </el-main>
        <el-footer>页脚</el-footer>
      </el-container>
    </el-container>
  </div>
</template>
<script>
export default {
  data() {
    return {
      swiperOption: {
        loop:true,
        centeredSlides: true,
        speed:500,
        autoplay: {
          delay: 2500,
          disableOnInteraction: false
        }
      }
    };
  },
  mounted() {
    console.log("app init", this);
    setTimeout(() => {
      // this.banners.push('/5.jpg')
      console.log("banners update");
    }, 3000);
    console.log(
      "This is current swiper instance object",
      this.mySwiper,
      "I will slideTo banners 3"
    );
    this.mySwiper.slideTo(3);
  }
};
</script>
<style>
html,
body {
  font-family: "Source Sans Pro", -apple-system, BlinkMacSystemFont, "Segoe UI",
    Roboto, "Helvetica Neue", Arial, sans-serif;
  font-size: 16px;
  word-spacing: 1px;
  -ms-text-size-adjust: 100%;
  -webkit-text-size-adjust: 100%;
  -moz-osx-font-smoothing: grayscale;
  -webkit-font-smoothing: antialiased;
  box-sizing: border-box;
}
.container {
  width: 100%;
  height: 100%;
}
.slide{
  width: 100%;
  height: 300px;
  overflow: hidden;
}
.swiper-slide img{
  width: 100%;
  height: 100%;
}
*,
*:before,
*:after {
  box-sizing: border-box;
  margin: 0;
}

.button--green {
  display: inline-block;
  border-radius: 4px;
  border: 1px solid #3b8070;
  color: #3b8070;
  text-decoration: none;
  padding: 10px 30px;
}

.button--green:hover {
  color: #fff;
  background-color: #3b8070;
}

.button--grey {
  display: inline-block;
  border-radius: 4px;
  border: 1px solid #35495e;
  color: #35495e;
  text-decoration: none;
  padding: 10px 30px;
  margin-left: 15px;
}

.button--grey:hover {
  color: #fff;
  background-color: #35495e;
}

.el-header,
.el-footer {
  background-color: #b3c0d1;
  color: #333;
  text-align: center;
  line-height: 60px;
}

.el-aside {
  background-color: #d3dce6;
  color: #333;
  text-align: center;
  line-height: 200px;
}

.el-main {
  background-color: #e9eef3;
  color: #333;
  text-align: center;
  line-height: 160px;
  height: 100%;
}

body > .el-container {
  margin-bottom: 40px;
  height: 100%;
}
.el-container {
  height: 100%;
}
.el-container:nth-child(5) .el-aside,
.el-container:nth-child(6) .el-aside {
  line-height: 260px;
  height: 100%;
}

.el-container:nth-child(7) .el-aside {
  line-height: 320px;
}
ul {
  list-style: none;
  display: flex;
  justify-content: space-around;
}
.el-container{
  display:block;
}
.el-main{
  overflow:inherit;
}
</style>
