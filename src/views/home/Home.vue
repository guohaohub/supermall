<template>
  <div id="home">
  <nav-bar class="home-nav"><div slot="center">购物街</div></nav-bar>
  <home-swiper :banner="banner"></home-swiper>
    <recommend-view  :recommend="recommend"></recommend-view>
  </div>
</template>

<script>
  import NavBar from "../../components/common/navbar/NavBar";
  import {getHomeMultidata} from "network/home";
  import HomeSwiper from "./childComps/HomeSwiper";
  import RecommendView from "./childComps/RecommendView";


  export default {
        name: "Home",
        components:{
          NavBar,
          HomeSwiper,
          RecommendView
        },
        data(){
          return {
            banner:[],
            recommend:[]
          }
        },
        created() {
          //1.请求多个数据
          getHomeMultidata().then( res=>{
            console.log(res);
            this.result = res;
            this.banner = res.data.banner.list;
            this.recommend = res.data.recommend.list;
            }
          )
        }
  }
</script>

<style scoped>
   .home-nav{
     background-color: var(--color-tint);
   }
</style>
