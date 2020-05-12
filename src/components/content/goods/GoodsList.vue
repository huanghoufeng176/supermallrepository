<template>
  <div class="">
    <good-list-item v-for="item in goods"
    
    :goodsItem="item">

    </good-list-item>
  </div>
</template>

<script>
import GoodListItem from './GoodListItem'
export default {
  props:{
    goods:{
      type:Object,
      default(){
        return {}
      }
    }
  },
  components:{
    GoodListItem
  },
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
</style>