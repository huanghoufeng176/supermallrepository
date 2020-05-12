<template>
  <div class="tab-control">
    <div v-for="(item,index) in titles" 
    class="tab-control-item"
    :key="item"
    @click="tabcontrolClick(index)"
    :class="{active:index==currentIndex}">
      <span>{{item}}</span>
    </div>
  </div>
</template>

<script>
export default {
  props:{
    titles:{
      type:Array,
      default(){
        return []
      }
    }
  },
  components:{},
  data(){
    return {
      currentIndex:0
    }
  },
  created(){},
  mounted(){},
  watch:{},
  computed:{},
  methods:{
    tabcontrolClick(index){
      // console.log(index)
      this.currentIndex=index
    }
  },
}
</script>
<style scoped>
  .tab-control{
    height: 49px;
    display: flex;
  }
  .tab-control-item{
    flex: 1;
    line-height: 49px;
    text-align: center;
  }
  .active span{
    padding: 5px;
    color: red;
    border-bottom: 3px solid red;
  }
  
</style>