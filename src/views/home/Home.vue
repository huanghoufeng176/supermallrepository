<template>
  <div class="home">
    <main-nav-bar></main-nav-bar>
    <home-swiper :banners="banners" class="banner"></home-swiper>
    <home-recomend :recommends="recommends"></home-recomend>
    <feature-view></feature-view>
    <tab-control :titles="['购物','新品','流行']" class="tab-control"></tab-control>
    <good-list :goods="goods['pop'].list"></good-list>




    <ul>
      <li></li>
      <li></li>
      <li></li>
      <li></li>
      <li></li>
      <li></li>
      <li></li>
      <li></li>
      <li></li>
      <li></li>
      <li></li>
      <li></li>
      <li></li>
      <li></li>
      <li></li>
      <li></li>
      <li></li>
      <li></li>
      <li></li>
      <li></li>
      <li></li>
      <li></li>
      <li></li>
      <li></li>
      <li></li>
      <li></li>
      <li></li>
      <li></li>
      <li></li>
      <li></li>
      <li></li>
      <li></li>
      <li></li>
      <li></li>
      <li></li>
      <li></li>
      <li></li>
      <li></li>
      <li></li>
      <li></li>
    </ul>
  </div>
</template>

<script>
//网络部分的导入
import {getHomeMultidata,getHomeGoods} from '../../network/home.js'

//导入组件
import MainNavBar from 'components/content/mainnavbar/MainNavBar.vue'
import HomeSwiper from './childrencoms/HomeSwiper.vue'
import HomeRecomend from './childrencoms/HomeRecomend'
import FeatureView from './childrencoms/FeatureView'
import TabControl from 'components/content/tabcontrol/TabControl.vue'
import GoodList from 'components/content/goods/GoodsList'

export default {
  components:{
    MainNavBar,
    HomeSwiper,
    HomeRecomend,
    FeatureView,
    TabControl,
    GoodList
  },
  data(){
    return {
      banners:[],
      recommends:[],
      goods:{
        'pop':{page:0,list:[]},
        'new':{page:0,list:[]},
        'sell':{page:0,list:[]},
      }
    }
  },
  created(){
    //1.请求多个数据
    this.getHomeMultidata()
    this.getHomeGoods('pop')
    this.getHomeGoods('sell')
    this.getHomeGoods('new')
  },
  mounted(){},
  watch:{},
  computed:{},
  methods:{
    getHomeMultidata(){
      getHomeMultidata().then(res=>{
        this.banners=res.data.banner.list
        this.recommends=res.data.recommend.list
      })
    },
    getHomeGoods(type){
      const page=this.goods[type].page+1
      getHomeGoods(type,1).then(res=>{
      console.log(res)
      this.goods[type].list.push(...res.data.list)
      this.goods[type].page+1
    })
    }
  },
}






</script>
<style scoped>
  .home{
    padding-top: 39px;
  }
  .tab-control{
    background-color: #fff;
    position: sticky;
    top: 39px;
  }
</style>