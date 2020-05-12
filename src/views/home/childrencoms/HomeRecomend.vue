<template>
  <div class="home-recomend">
    <div v-for="item in recommends" :key="item.image" class="recomend-item">
      <a :href="item.link">
        <img :src="item.image" alt="">
      </a>
      <p>{{item.title}}</p>
    </div>
  </div>
</template>

<script>
export default {
  props:{
    recommends:{
      type:Array,
      default(){
        return []
      }
    }
  },
  components:{},
  data(){
    return {
    }
  },
  created(){},
  mounted(){},
  watch:{},
  computed:{},
  methods:{},
}
</script>
<style scoped>
.home-recomend{
  display: flex;
  font-size: 12px;
  text-align: center;
  border-bottom: 8px solid #f6f6f6;
  padding-left: 6px;
  padding-right: 6px;
}
.recomend-item{
  flex: 1;
}
.recomend-item img{
  width: 55px;
  height: 55px;
  margin-top: 5px;
}
.recomend-item p{
  margin-top: 3px;
}
</style>